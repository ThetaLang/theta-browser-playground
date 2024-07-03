theta --emitAST -o out.wasm test.th

browser-sync start --server --files "test.wasm"

http-server -c-1
