📌 **Axios** is  ==a widely-used JavaScript Library for making HTTP requests from Browser and Node.js.==

```ts
import axios from axios;
await axios.get('endpoint', (res)=> res.data);
```

📌create a **axios** **instance**

```ts
const axiosInstance = axios.create({
  baseURL: "https://api.themoviedb.org/3",
  params: { api_key: VITE_TMDB_API_KEY },
  headers: {
    Accept: "application/json",
  },
});
```

📌create a **API Client** class

```ts 
class ApiClient<T> {//customize based on your usecase
  private endpoint: string;

  constructor(endpoint: string) {
    this.endpoint = endpoint;
  }
  get = async () => {
    return axiosInstance.get<T>(this.endpoint).then((res) => res.data);
  };
  getAll = async (params?: AxiosRequestConfig) => {
    return axiosInstance
      .get<FetchResponse<T>>(this.endpoint, params)
      .then((res) => res.data);
  };
}
export default ApiClient;
```
