# Setup the Google Colab to run Ollama

1. Create a new Google Colab notebook and open it in your browser.
2. Click on `Runtime` tab, then click on `Change runtime type`. You will see a pop-up window. Choose `T4 GPU` as the Hardware accelerator
3. Register an account at <a href="https://ngrok.com/">ngrok</a> and create an `authtoken` by navigating to `Your Authtoken` section and replace place it in the `Colab` notebook
4. Click on `Code` as mentioned in the screenshot ![Select Code](select_code.png)
5. Execute the following command in the terminal
    - <code>!curl https://ollama.ai/install.sh | sh</code>
    -   <code>
            !pip install aiohttp pyngrok

            import os
            import asyncio

            # Set LD_LIBRARY_PATH so the system NVIDIA library 
            os.environ.update({'LD_LIBRARY_PATH': '/usr/lib64-nvidia'})

            async def run_process(cmd):
            print('>>> starting', *cmd)
            p = await asyncio.subprocess.create_subprocess_exec(
                *cmd,
                stdout=asyncio.subprocess.PIPE,
                stderr=asyncio.subprocess.PIPE,
            )

            async def pipe(lines):
                async for line in lines:
                print(line.strip().decode('utf-8'))

            await asyncio.gather(
                pipe(p.stdout),
                pipe(p.stderr),
            )

            await asyncio.gather(
                run_process(['ngrok', 'config', 'add-authtoken','YOUR_AUTH_TOKEN_HERE'])
            )

            await asyncio.gather(
                run_process(['ollama', 'serve']),
                run_process(['ngrok', 'http', '--log', 'stderr', '11434', '--host-header', 'localhost:11434'])
            ) 
        </code>
6. It should produce something like:<br>
        `starting ollama serve`<br>
        `Couldn't find '/root/.ollama/id_ed25519'. Generating new private key.`<br>
        `Your new public key is:`<br>
        `ssh-ed25519 {some key}`<br>
7. Follow the steps mentioned in `README.md` under <b>[`Steps to try the crewai-Ollama-mistral-example`](../README.md#steps-to-try-the-crewai-ollama-mistral-example) </b>