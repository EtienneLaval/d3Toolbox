# d3Toolbox

# SubProjects
## ColorSplitter 
It is all about plitting colors on a range that makes multiple charts showing parially shared datasets consistent colorwise while keeping esthetic cf [poc/color-splitter](https://github.com/EtienneLaval/d3Toolbox/tree/poc/color-splitter)
### Set splits:
1. Vector Simple : 
Merge all label and use a simple long vector of them
2. Vector Sorted :
= Vector Simple + Nth occurences >= N+1th occurences 
3. Tree: 
* parent branch occurence > child branch occurence 
* parent node occurence = child node occurence 

* Data model 
```
branch = [node_0, ..., node_N]
tree = [branch_0, ..., branch_M] 
```


### Color splits:
1. Vector 
scatter evenly along a set of colorKeys 
2. Bezier 
scatter evenly along an bezier interpolation of colorKeys
3. Graph 
- cool if the common colors are separatred by lots of less used colors.
- split scattering in different directions if several edges in a graph: 2 connex edges can't ave the same 2 nodes + respect a minimum distance between colors (for ovelaping edges)
- Implementation idea : get a complete graph between colorKeys with max color by edge (modulo who owns the overlap), then browse the graph accordingly

# How To :

*  Project setup
```
npm install
```
* Compiles and hot-reloads for development
```
npm run serve
```

* Compiles and minifies for production
```
npm run build
```

* Run your unit tests
```
npm run test:unit
```

* Lints and fixes files
```
npm run lint
```
