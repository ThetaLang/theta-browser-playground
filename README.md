# Theta Playground

Theta Playground is an interactive web-based environment for experimenting with WebAssembly (WASM) modules generated from the Theta programming language. It provides a simple and intuitive interface to load, display, and execute WebAssembly code directly in the browser.


![Screen Shot 2024-07-03 at 1 58 30 AM](https://github.com/alexdovzhanyn/theta-browser-playground/assets/9296866/16357e85-5f9b-40e1-9ce1-44bff4f9ae49)

## IMPORTANT
Theta implements some experimental WebAssembly features. In order for the browser to support all of Theta's language features, make sure "Experimental WebAssembly" is enabled in `chrome://flags/`:

![Screen Shot 2024-07-03 at 5 12 47 PM](https://github.com/alexdovzhanyn/theta-browser-playground/assets/9296866/346aa179-51b0-4a5a-b767-e26dedf057d7)


## Key Features

- **Dynamic WebAssembly Loading**: The playground dynamically fetches and loads WebAssembly modules specified in a configuration file (`wasmSource.json`), allowing for easy updates and modifications without changing the HTML structure.
- **Hexdump Display**: Visualize the binary content of the loaded WebAssembly module in a hexdump format, helping users understand the raw binary data.
- **Console Output Redirection**: JavaScript console outputs are redirected to an on-screen console, making it easier to debug and observe the program's behavior in real-time.
- **Execution of WebAssembly Functions**: Execute exported functions from the WebAssembly module and display the results, providing immediate feedback on the execution.

## Project Structure

- **index.html**: The main HTML file that sets up the playground interface.
- **watch_source.sh**: A shell script to monitor changes in the source Theta file, recompile it to WASM, and refresh the playground automatically.

## Usage

To set up the Theta Playground, follow these steps:

1. **Clone the Repository**:
    ```sh
    git clone https://github.com/alexdovzhanyn/theta-browser-playground.git
    cd theta-playground
    ```

2. **Ensure fswatch is Installed**:
    Install `fswatch` if it's not already installed on your system. On macOS, you can use Homebrew:
    ```sh
    brew install fswatch
    ```

    On Linux, you can follow the instructions for your distribution to install `fswatch`.

3. **Ensure browser-sync is Installed**:
    Install `browser-sync` if it's not already installed on your system:
    ```sh
    npm i -g browser-sync
    ```

4. **Run the Script**:
    The `watch_source.sh` script will start a local server using `browser-sync` and open your default browser to `localhost:3000`.
    ```sh
    ./watch_source.sh path/to/theta/source/file.th
    ```
