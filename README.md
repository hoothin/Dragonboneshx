dragonboneshx
==================

This is a HaXe3+openfl port of the DragonBones (http://dragonbones.github.io/index.html)

fork from https://github.com/jalbanesi/openfl-dragonbones

Usage:

```Haxe
haxelib git dragonbones https://github.com/hoothin/dragonboneshx
```

- Code:

```Haxe
  // U can do this after res not from assets loaded
  ArmatureManager.instance.parseData(     
    Assets.getText("assets/Dragon/skeleton.xml"), 
    Assets.getText("assets/Dragon/texture.xml"),
    Assets.getBitmapData("assets/Dragon/texture.png") 
  );
  var armature: Armature = ArmatureManager.instance.buildArmature("Dragon");
  WorldClock.clock.add(armature);
  WorldClock.clock.isOpen = true;
  armature.display.x = 300;
  armature.display.y = 500;
  Lib.current.addChild(armature.display);
  armature.animation.gotoAndPlay("walk");
```

- Access individual bones and child armatures:  

```Haxe
  var bone: Bone = armature.getBone("aBone");
  bone.childArmature.animation.gotoAndPlay("run");
```
