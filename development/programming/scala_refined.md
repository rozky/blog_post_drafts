Refined by examples
===================

- https://kwark.github.io/refined-in-practice
- http://fthomas.github.io/talks/2016-05-04-refined
- https://vlovgr.github.io/refined-types/
- https://underscore.io/blog/posts/2017/03/07/refined-data-config-database.html

## Create Refined value from string literal

```scala
package com.roozky.matchbook.domain.model

import com.roozky.matchbook.domain.model.PageSize.PageSizeNumber
import eu.timepit.refined.W
import eu.timepit.refined.api.{RefType, Refined}
import eu.timepit.refined.numeric.Interval

final case class PageSize(value: PageSizeNumber)

object PageSize {
  type PageSizeNumber = Refined[Int, Interval.Closed[W.`1`.T, W.`1000`.T]]

  val `1000` = PageSize(RefType.applyRefM[PageSizeNumber](1000))
}
```

## Combining predicates

```scala
package com.roozky.matchbook.domain.model

import com.roozky.matchbook.domain.model.SessionToken.SessionTokenStr
import eu.timepit.refined.W
import eu.timepit.refined.api.Refined
import eu.timepit.refined.boolean.{AllOf, Not}
import eu.timepit.refined.collection.{Empty, MaxSize}
import eu.timepit.refined.string.Trimmed
import shapeless.{::, HNil}

final case class SessionToken(token: SessionTokenStr)

object SessionToken {
  type SessionTokenStr = Refined[String, AllOf[Trimmed :: Not[Empty] :: MaxSize[W.`50`.T] :: HNil]]
}
```
