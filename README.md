# Create and save embeddings from posted text

If you want to build locally, make sure you have installed Rust and added the `wasm32-wasi` target.

```
cargo build --target wasm32-wasi --release
```

Reset the database and add embeddings from a file. Each file could contain multiple text segments. Each segment corresponds to an 
embedding. The text sgements are seperated by blank lines in the text file, with exception of blank lines in code listings.
Each code listing always belong to a segment, and it is never broken up.

```
curl "https://code.flows.network/lambda/2tVDJrikvo?collection_name=my_kb&vector_size=1536&reset=1" -X POST --data-binary "@test1.txt"
```

Append the database and add embeddings from a file

```
curl "https://code.flows.network/lambda/2tVDJrikvo?collection_name=my_kb&vector_size=1536" -X POST --data-binary "@test2.txt"
```

