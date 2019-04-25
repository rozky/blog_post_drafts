```scala
import eu.timepit.refined.W
import eu.timepit.refined.api.{RefType, Refined}
import eu.timepit.refined.numeric.Interval

case class PageSize(value: PageSizeNumber)

object PageSize {
  type PageSizeNumber = Refined[Int, Interval.Closed[W.`1`.T, W.`1000`.T]]

  val `1000` = PageSize(RefType.applyRefM[PageSizeNumber](1000))
}
```
