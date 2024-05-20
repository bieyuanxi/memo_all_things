# Terrian Builder
A collection of terrian builders of different terrians. There are many terrians: Forest, Desert, Ocean, Underground, Hell, Cave, BloodRed, Crrupt, Holiness and so on.(I don't really know is the name right.)
## Seed number
The input seed number is 8 bytes. For example: 0x1234abcd9876fedc.

Seed number can decide: 
```
map name: Each map has a name, which can be modified by user later.
Where and which terrian builder is used.
```


According to input, generate a TerrianMap.
## Terrian Input Parser
Each terrian builder has a parser, turn seed into config.

```
Config {}

trait TerrianBuilder{
    pub fn build();
}
```

## BuildTask
```
struct BuildTask {
    area: Rectangle
    ...
}
```