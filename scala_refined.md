```
import eu.timepit.refined.W
import eu.timepit.refined.api.{RefType, Refined}
import eu.timepit.refined.numeric.Interval

case class PageSize(value: Max1000)

object PageSize {
  type Max1000 = Refined[Int, Interval.Closed[W.`1`.T, W.`1000`.T]]

  val `1000` = PageSize(RefType.applyRefM[Max1000](1000))
}
```
