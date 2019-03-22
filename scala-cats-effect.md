Working with cats effect (like IO) using abstractions
======================================================

#### working with Parallel[F[_], G[_]] where F[_] is IO[_] and G[_] god know what but I know I had hard time figure it out luckily 
(cats-par)[https://github.com/ChristopherDavenport/cats-par] come to rescue 

#### What is `*>`

```
package com.roozky.example.cats

import cats.implicits._
import cats.effect.{ExitCode, IO, IOApp}

/**
  * Shows used of *> which is shorter syntax for doing x.flatMap(_ => ...)
  */
object SequenceIndependentEffectsApp extends IOApp {
  override def run(args: List[String]): IO[ExitCode] = {
    IO(println("Hello World")) *> IO.pure(ExitCode.Success)
  }
}
```
