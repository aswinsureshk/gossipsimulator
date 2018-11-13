# Project2

The goal of this project is to determinethe convergence of such algorithms through a simulator based on actors writtenin Elixir.  Since actors in Elixir are fully asynchronous, the particular type ofGossip implemented is the so calledAsynchronous Gossip.Gossip  Algorithm  for  information  propagation. The  Gossip  algorithminvolves the following:

•Starting:A participant(actor) it told/sent a roumor(fact) by the mainprocess

•Step:Each actor selects a randomneighboorand tells it the roumor

•Termination:Each actor keeps track of rumors and how many times ithas heard the rumor.  It stops transmitting once it has heard the roumor10 times (10 is arbitrary, you can play with other numbers or other stopingcriterias).

Push-Sum algorithm for sum computation

•State:Each actorAimaintains two quantities:sandw.  Initially,s=xi=i(that is actor numberihas valuei, play with other distribution ifyou so desire) andw= 1•Starting:Ask one of the actors to start from the main process.

•Receive:Messages sent and received are pairs of the form (s, w).  Uponreceive,  an actor should add received pair to its own corresponding val-ues.  Upon receive, each actor selects a random neighboor and sends it amessage.

•Send:When sending a message to another actor, half ofsandwis keptby the sending actor and half is placed in the message.•Sum  estimate:At  any  given  moment  of  time,  the  sum  estimate  isswwheresandware the current values of an actor.

•Termination:If an actors ratioswdid not change more than 10−10in3 consecutive rounds the actor terminates.WARNING: the valuessandwindependently never converge, only the ratio does

.TopologiesThe actual network topology plays a critical role in the dissemi-nation speed of Gossip protocols.  As part of this project you have to experimentwith various topologies.  The topology determines who is considered a neighboorin the above algorithms.

•Full  NetworkEvery  actor  is  a  neighboor  of  all  other  actors.   That  is,every actor can talk directly to any other actor.

•3D Grid:Actors form a 3D grid.  The actors can only talk to the gridneigboors.

•Random 2D  Grid:Actors  are  randomly  position  at  x,y  coordinnateson a [0-1.0]X[0-1.0] square.  Two actors are connected if they are within.1 distance to other actors.

•Sphere:Actors  are  arranged  in  a  sphere.   That  is,  each  actor  has  4 neighbors (similar to the 2D grid) but both directions are closed to formcircles.

•Line:Actors are arranged in a line.  Each actor has only 2 neighboors(one left and one right, unless you are the first or last actor).

•Imperfect Line:Line arrangement but one random other neighboor isselected from the list of all actors.

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `project2` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:project2, "~> 0.1.0"}
  ]
end
```

Documentation can be generated with [ExDoc](https://github.com/elixir-lang/ex_doc)
and published on [HexDocs](https://hexdocs.pm). Once published, the docs can
be found at [https://hexdocs.pm/project2](https://hexdocs.pm/project2).

