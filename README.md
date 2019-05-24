## ReactHooks

ReactHooks の使い方について学習

1. axios
2. JSONPlaceholder[https://jsonplaceholder.typicode.com]

### ライフサイクルメソッドの使い方を学ぶ

```javascript
import { useState, useEffect } from "react";
import axios from "axios";
const useResources = resource => {
  const [resources, setResources] = useState([]);

  useEffect(() => {
    (async resource => {
      const response = await axios.get(
        `https://jsonplaceholder.typicode.com/${resource}`
      );

      setResources(response.data);
    })(resource);
  }, [resource]);
  return resources;
};

export default useResources;
```
