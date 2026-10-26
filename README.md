# MG4
## Devlog
The floating animates the FoodObjects up and down like so: two variables named _up (Boolean) and _timer (Float) are defined and given the default value of False (in the case of _up) and set to the value of _switchSpeed, or the value as specified in the FloatAnimation Component's "switch speed" field, in Start(), respectively.

From here, the actual animation behavior is controlled in Update(). An "if/else" statement is present and constructed in such a way that if _up is true, the Transform component that FloatAnimation.cs is a Component of applies a positive y-axis modulation by a product of the move speed (_moveSpeed) and the time passed since last frame (Time.deltaTime) using Transform's Translate() method, and performs a negative y-axis modulation in the same manner if _up is false. Then, _timer is decremented by the amount of time passed since last frame. From here, Update() checks if _timer is zero or a negative float value, and if so, _timer is reset and _up is set to the opposite boolean value (true -> false, false -> true).

Thanks to Update() being automatically called every frame in FloatAnimation.cs, this essentially causes the FoodObject to move down per frame according to its defined move speed until the timer runs out, at which point the FoodObject switches direction, begins to move up, and the timer is reset to its starting value.

## Open-Source Assets
- [Quirky animal 3D models](https://assetstore.unity.com/packages/3d/characters/animals/quirky-series-free-animals-pack-178235)
- [City 3D models](https://assetstore.unity.com/packages/3d/environments/simplepoly-city-low-poly-assets-58899)
- [Bite sound effect](https://freesound.org/people/Jofae/sounds/353067/)