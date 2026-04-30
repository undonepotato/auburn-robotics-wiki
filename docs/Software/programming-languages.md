# Programming Languages
The most common programming languages used in VEX are block code, Python, and C/C++, though some teams also use Rust through `vexide`. Each generally serves a different purpose.

## Blocks
Block code is by far the easiest to get started with, and most competitors have some understanding of how block code works. Though wider community support is lacking and block code can become cumbersome for larger projects, you won’t find a faster development experience anywhere.

In VEX, the environment is offered via VEXCode Blocks, available on Windows, Mac, iPadOS, Android, and the Web (for Windows, Mac, and ChromeOS).

### Features
* Incredibly accessible; generally editable by everyone on the team if necessary.
* Very quick to program in.
* Easy manipulation of devices through a dedicated GUI. Motors and sensors and their properties can be added through the Devices panel on the right-hand side of the app; this is also where motors can be reversed and general settings can be changed.
* Two- and four-motor drivetrains are automatically handled as separate devices for easy onboarding.
* Almost all features of text-based programming languages’ VEX-specific APIs are provided; you can spin motors, get sensor values, and do all the math you would reasonably need.
    * There are some exceptions, like not being able to command a raw voltage to motors and relying on the built-in PID for velocity.
* Most procedural programming constructs are provided; there are numeric, boolean, and array data types, and user-defined functions (“blocks”) are possible.
* Equivalent code in Python or C++ is viewable, though not editable. This gives a starting point for migration.
### Limitations
* All variables in VEXCode Blocks are global, which makes larger projects more cumbersome.
* No support for object-oriented or functional programming.
* Block code can get more difficult to organize for larger projects, partially due to the impossibility of file splits.
* Arrays are always of a fixed size, with the maximum size being 20 in each dimension.
* No string data type or more advanced types, like hashmaps/dictionaries.
* Very limited community support; you can’t use external code, so advanced functionality must be implemented entirely solo. Viewed by some teams as a stepping stone unsuitable for “real” work.
* No support for concurrent programming or tasks, though events exist.
* Much slower than text-based languages. Shouldn’t be too much of a problem for most routines, but could be an issue for very frequent math for odometry or similar.
* Only the official VEXCode app is supported, which does not have Git integration, extensions, an integrated terminal, or other facilities.
### Use cases
* Quick prototyping or testing of components.
* General code without complex odometry or other advanced features.
* Learning procedural logic, algorithms, and data structures.

## Python
Python is often used outside the VEX community, but there are fewer facilities for this language within the community than there are for C++ in general.

### Features
* Facilities of a full programming language supporting procedural, functional, and object-oriented paradigms as well as all common variable types and variable scoping.
* Quicker to program in than C++ in general.
* Marginally faster than block code, but still much slower than C++.
* Multi-file support (though see below).
* Very basic support for concurrent programming (also see below).
### Limitations
* Multi-file support requires loading non-main files onto a microSD card.
* Concurrent programming support is very limited and vulnerable to issues with more complex setups; there are no synchronization mechanisms in the built-in Thread API.
    * uasyncio may be an option, though untested.
* Dynamic typing can be prone to issues without type hinting and careful programming.
* Runtime errors can lead to issues mid-match.
* Still limited community support; no unified pipeline for external code. No large public library ecosystem.
    * Loading external code is possible ad-hoc through the SD card system.
* Automatic memory management and the interpreted nature of the language makes it still slower than C++.
### Use Cases
* Teams that already have experience with Python.
* Teams learning text code that don’t want the greater complexity of C++.
* Teams that want the language features of a text-based language to implement advanced features and are willing to deal with rough edges.

## C/C++
The most common language among high-performing VEX teams, as well as the most complex language option. Powerful, but can be dangerous.

### Features
* Complete language support for advanced programming features.
* A complete and developed ecosystem of APIs, external libraries, and learning resources specifically for VEX.
    * PROS is commonly used, but the official VEX library’s historical issues with documentation are largely fixed now, so it is also a workable option.
    * Prebuilt libraries for odometry like LemLib and EZTemplate accelerate programming.
* Full-featured concurrent programming facilities with mutexes, semaphores, and events enable safe, complex code.
* Static typing means errors are often caught at compile time, reducing breakdowns on the field.
* Compiled and therefore faster in runtime than the other two languages.
### Limitations
* A generally complex language with many nuances. More difficult to learn than either Blocks or Python.
* Slower to code in than other options.
* It is entirely possible to write unsafe code that leads to memory leaks, inefficiencies, or undefined behavior. Discipline and good programming practices are required for doing anything beyond the most simple library use.
### Use Cases
* Teams wanting more complex code or advanced features.
* Teams that want maximum flexibility with the capabilities of their code without having to consider a switch—C++ will likely stay supported forever by the community.
* Teams that have skilled programmers or those that are willing to learn.

## Rust
!!! note "Needs expansion"
    This section requires further content.

Rust is less commonly used among VEX teams, but the open-source `vexide` project enables use of the language. In the wider developer community, it is generally considered as powerful as C++ but also much safer in terms of memory usage.

```py
print("hello world!")
my_list = []
for i in range(40):
    my_list.append(i ** 2 / 34)
    my_list.reverse()
print(my_list)
```
```
mi
m
```
