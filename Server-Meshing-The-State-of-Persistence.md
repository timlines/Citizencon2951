Entities that entering the streaming buble

Entity bind culling

Poor distribution of players, the player being at every single location.

Allow multiple instances of the game server.

# Architecture

Client server called an instance with up to 50 players.

When a DGS instance is created it has a unique copy of each item in stanton, the entities are deleted with the server is shut down.

# Replication Layer

The goal of server meshing

The best we we can scale this to infinity.

We have to find a good way to syncronize the server and the client.

We are seperating

Replication layer

-It hold the state of every entity in memory
-Replicates the state to server nodes and clients

# Shards and Persistent streaming

A shared is a unique version of the universe, but the server mesh increases the number players on each shard.

Seeding occurs with the entity graph database

# Persistence

The Entity graph

Stores game data as a graph. Data structures that the game uses, nodes and edges.

Game objects are conisted of game entities.

A ship is made up of several entities, holding properties, the edge tells it how it is connected to the root. An item is the agragate route distinguisted with a label.

oc- object containers.

For each entity node a snapshot is created and variable can persist based on given inputs.

A graph data reduces writes. 

The entire world is composed of these entity graphs

# Seeding

A new database is created by the replication layer, millions of entities are created a type of big bang.

Static entities
Dynamic entities - anything you can interact with.

# Global vs Shard Data

It would be terrible if you lost data in a shard.

Stowed and unstowed entities.

Entities live a global database. 

Personal inventories, cargo inventories, stowed in the global database.

# Benefits and Challenges

No synchronyzation

The same streaming and replication is applied to servers

more resilance, the client stays connected even if the sever crashes

Underlying challenged

A static mesh will come first

Many parts of the game are effected by the server meshing, when you connect to a game server, this concept will need to change to subscribe to different servers. Missions will need to be spawn globally, all system will need to now be connected globally. 

Global chat also needs to be extended to a shard, many features need to change to accominate a mesh of servers. 