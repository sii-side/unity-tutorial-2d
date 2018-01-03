# Base Article

- [【Unity2D】Unityで2Dミニゲームを作るチュートリアル（第１回）](https://qiita.com/2dgames_jp/items/11bb76167fb44bb5af5f#_reference-3e689b5ba7bdf8c7aa3f)

# Environment

- Windows10 64bit
- Unity3d 2017.3.0f3 Personal

# Fix error for this version

- GameMgr.cs
- TitleMgr.cs
```diff
+using UnityEngine.SceneManagement;

-Application.LoadLevel("Title");
+SceneManager.LoadScene("Title");
```

- Token.cs
```diff
 public float Direction {
   get {
-    Vector2 v = rigidbody2D.velocity;
+    Vector2 v = GetComponent<Rigitbody2D>()
     return Mathf.Atan2 (v.y, v.x) * Mathf.Rad2Deg;
   }
 }

 public float Speed {
   get {
-    Vector2 v = rigidbody2D.velocity;
+    Vector2 v = GetComponent<Rigitbody2D>()
     return Mathf.Sqrt (v.x * v.x + v.y * v.y);
   }
 }
```