FlatBuffers swift can be found in both SPM

`.package(url: "https://github.com/arcturus-industries/flatbuffers-swift.git", from: "X.Y.Z"),`

and Cocoapods

`pod 'FlatBuffers'`

### Notes

1- To report any error please use the main repository.

2- `1.0.0` deprecates `MyGame_Example_Vec3.createVec3(builder: &fbb, x: 10, test2: .blue)` for `MyGame_Example_Vec3(x: 10, test2: .blue)`. This uses Swift native structs instead of workarounds that which leads to a huge performance increase when serializing structs. You can download the [binary here](https://github.com/google/flatbuffers/actions) and select the latest push to master

### Contribute

1- Always run `swift test --generate-linuxmain` whenever new test functions are added or removed



### Pulling upstream changes

If you don't have `upstream-master` yet, create it

```
git remote add upstream https://github.com/google/flatbuffers
git fetch upstream
git checkout -b upstream-master upstream/master
```
Pull the latest changes from upstream into `upstream-swift`

```
git checkout upstream-master
git pull
git subtree split --prefix=swift --onto upstream-swift -b upstream-swift
```
Rebase our changes (if any) onto `upstream-swift`

```
git checkout main
git rebase upstream-swift
```
Finally, push the changes to our fork

```
git push origin main
```

