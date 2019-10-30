# memoncpp

memoncpp is a C++17 header-only .memon file parsing library with [nlohmann::json](https://github.com/nlohmann/json) as its sole dependency

.memon is a new json-based jubeat memo format designed to be easier to parse than existing memo formats.
The goal of this format is to allow for easier and faster creation of tools and simulators.

## usage

```cpp
#include <fstream>
#include <iostream>
#include "include/memon.hpp"

int main(int argc, char const *argv[]) {
    
    stepland::memon m;
    std::ifstream file("test.memon");
    file >> m;
    
    std::cout << "test.memon has " << m.charts.size() << "charts" << '\n';
    for (auto& [difficulty, chart] : m.charts) {
        std::cout << difficulty << " : " << chart.level << '\n';
    }
    return 0;
}
```
