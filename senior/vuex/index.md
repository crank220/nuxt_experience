## vuex-persistedstate

[vuex 长储存](https://www.npmjs.com/package/vuex-persistedstate)

### vuex-persistedstate 推荐 secure-ls

```javascript
import { Store } from "vuex";
import createPersistedState from "vuex-persistedstate";
import SecureLS from "secure-ls";
var ls = new SecureLS({ isCompression: false });
 
// https://github.com/softvar/secure-ls
 
const store = new Store({
  // ...
  plugins: [
    createPersistedState({
      storage: {
        getItem: key => ls.get(key),
        setItem: (key, value) => ls.set(key, value),
        removeItem: key => ls.remove(key)
      }
    })
  ]
});
```

### 通过高级别的加密和数据压缩来保护localStorage数据
[github](https://github.com/softvar/secure-ls)  
[secure-ls home](https://varunmalhotra.xyz/secure-ls/#docs)