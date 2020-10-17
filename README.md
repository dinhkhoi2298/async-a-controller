# async-a-controller

[![sampctl](https://img.shields.io/badge/sampctl-async--a--controller-2f2f2f.svg?style=for-the-badge)](https://github.com/roesanne26/async-a-controller)

<!--
Short description of your library, why it's useful, some examples, pictures or
videos. Link to your forum release thread too.

Remember: You can use "forumfmt" to convert this readme to forum BBCode!

What the sections below should be used for:

`## Installation`: Leave this section un-edited unless you have some specific
additional installation procedure.

`## Testing`: Whether your library is tested with a simple `main()` and `print`,
unit-tested, or demonstrated via prompting the player to connect, you should
include some basic information for users to try out your code in some way.

And finally, maintaining your version number`:

* Follow [Semantic Versioning](https://semver.org/)
* When you release a new version, update `VERSION` and `git tag` it
* Versioning is important for sampctl to use the version control features

Happy Pawning!
-->

## Installation

Simply install to your project:


```bash
sampctl package install roesanne26/async-a-controller
```

Include in your code and begin using the library:

```pawn
#include <async-a-controller>
```
## Dependencies

<https://github.com/IllidanS4/PawnPlus/>
## Usage
Function: `Task:async_controller_show`
```pawn
#include <Async-A_Controller>

CMD:dancing(playerid) {
	task_yield(1);
	SetPlayerSpecialAction(playerid, 5);
	new 
		result = task_await(async_controller_show(playerid));
	
	if(result) 
		SendClientMessage(playerid, 0xFFFF00AA, "[DANCING]: Ban da hoan thanh thu thach");
	
	else 
		SendClientMessage(playerid, 0xFF6347AA, "[DANCING]: Ban da that bai thu thach");

	ClearAnimations(playerid);
	SetPlayerSpecialAction(playerid, 0);
	TogglePlayerControllable(playerid, true);
	SetCameraBehindPlayer(playerid);
	return 1;
}

```

<!--
Write your code documentation or examples here. If your library is documented in
the source code, direct users there. If not, list your API and describe it well
in this section. If your library is passive and has no API, simply omit this
section.
-->

## Testing

<!--
Depending on whether your package is tested via in-game "demo tests" or
y_testing unit-tests, you should indicate to readers what to expect below here.
-->

To test, simply run the package:

```bash
sampctl package run
```

## Credits

- Ares: Original script (https://github.com/AresVN/a_controller)

- Me: Make async version
