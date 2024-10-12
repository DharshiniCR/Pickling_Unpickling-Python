# Pickling & Unpickling

## Pickle
The **Pickle module** accepts any Python object, converts it into a string representation, and dumps it into a file using the `dump` function.

## Unpickle
**Unpickling** is the process of retrieving the original Python object from its string representation using `load` function.

### NOTE
- **Security Warning:**
  - Do not unpickle data from untrusted sources, as it can execute arbitrary code during deserialization, which poses a security risk.
- **Picklable Objects:**
  - Not all Python objects can be pickled.
  - Objects like open file handles, network connections, and database connections cannot be pickled.

Pickling is a powerful way to serialize Python objects for storage or transfer, while unpickling allows you to restore these objects. This can be useful for saving program state or exchanging data between processes.

## Real-Time Use Cases
- In **machine learning**, trained models often need to be saved and later reused without retraining. Pickling is commonly used to save the trained model to a file, and unpickling is used to load the model back when needed.
- In web applications, pickling can be used to **cache data** so that expensive computations (such as database queries or API calls) don't need to be repeated. By pickling the result of the computation and storing it in a cache, subsequent requests can quickly retrieve the result by unpickling the cached data.
- In distributed systems or parallel processing, data often needs to be **transferred between different processes**, threads, or nodes. Pickling allows complex Python objects to be serialized into a format that can be sent across the network or shared between processes.
- Web scrapers often need to save large amounts of data, such as parsed HTML or structured data. Pickling can be used to **save the entire scraped dataset** to a file, and unpickling can restore it for later analysis.
- In some web frameworks, such as Flask, pickling is used to **store user session data**. The session data is serialized into a cookie or server-side storage and unpickled when the user returns.
- In game development, you may want to allow players to save and load their progress. Pickling can be used to **save the entire game state** (player progress, inventory, scores, etc.) to a file, and unpickling restores the game state when loading.
- In **data pipelines** where preprocessing steps or intermediary results need to be saved for reuse, pickling can be used to store and retrieve these results without recalculating them.
