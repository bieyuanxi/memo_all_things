# Basic Concepts

## Item & ItemID
An item equals itemID + Sprite + and so on.
Each itemID is unique, size 2 bytes, allowing max 65536 unique items.

ItemID starts from 0x1. 0x0 is not used.

## Entity & EntityID
An entity is a instance obj of itemID in game.

## TerrianMap
The Map, is an array which contains all entities in game. Index is position, values are itemIDs.
```
terrianMap[10][8] => the itemID of the entity in position (10, 8).
```
For items that bigger than one position, only one position is set to item, leaving rest empty. A bitmap should used to represent those are occupied.

The max entity count of a map contains is 3000*5000.
```
entity count = 3000*5000 = 15,000,000 = 15 million!

A map size: 3000*5000*2 bytes = 28.6MB
```

## TerrianBitMap
