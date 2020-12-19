# Instalar el blog

En 'Máquina Local' se usa la plantilla de Jekyll 'Minimal Mistakes' para la creación del contenido. La mejor manera de crear un artículo es que repliques el entorno en tu máquina local :grin:. Puedes hacerlo siguiendo estos pasos:

## Instalación

### Instalación de Ruby en Ubuntu

Instalar 

```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```

Después de esto, configuramos las gemas de Ruby :gem: agregando el siguiente fragmento a la configuración de tu terminal. Ejecutando estas órdenes lo tienes:

```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### Instalación de Jekyll

```bash
gem install jekyll bundler
```

Fíjate que no hemos tenido que usar `sudo` en ninguna instrucción :wink:

## Running Jekyll Serve

By default, the Jekyll server is launched with the following command (which is the one indicated on your website).

```bash
bundle exec jekyll serve
```

If in the process of building the server there is a dependency problem, for example, there is a missing library to install, it is **necessary to delete** the `Gemfile.lock` file so that it is rebuilt with the installed dependency. This list of dependencies is found in the `Gemfile` file (in Python it would be equivalent to the `requirements.txt` file) and the version of each of the installed gems (packages) is specified. Having a list of dependencies is important for future updates as well as knowing the libraries needed to run the server. Once the `Gemfile.lock` file is deleted, the command shown above is launched again and the dependency errors should end.


## FAQ

- Error construyendo el servidor de Jekyll: 

    ```bash
    jekyll build --incremental --verbose
    ```

- Actualizar `Rubygems`, `bundler` y `Gemfile.lock`:

  ```
  warn_for_outdated_bundler_version': You must use Bundler 2 or greater with this lockfile. (Bundler::LockfileError)
  ```

  To use Bundler 2 in your `.lockfile`:

  #### Actualizar Rubygems

  ```
  gem update --system
  ```

  #### Actualizar el *bundler*

  ```
  gem install bundler
  ```

  #### Actualizar `Gemfile.lock` del proyecto

  ```
  bundler update --bundler
  ```