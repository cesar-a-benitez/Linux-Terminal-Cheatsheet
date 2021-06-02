# Guia Básico de Comandos Linux

## Sumário

- [Guia Básico de Comandos Linux](#guia-básico-de-comandos-linux)
  - [Sumário](#sumário)
  - [Atalhos](#atalhos)
  - [Links de Referência](#links-de-referência)
  - [Instruções](#instruções)
  - [Comandos Básicos](#comandos-básicos)
  - [Parâmetros](#parâmetros)
  - [Multiplos Comandos](#multiplos-comandos)
  - [Instalar Programas](#instalar-programas)
    - [Programas Baixados da Internet](#programas-baixados-da-internet)
    - [Sistemas Baseados em Arch Linux](#sistemas-baseados-em-arch-linux)
      - [AUR](#aur)
      - [Parâmetros PACMAN](#parâmetros-pacman)
      - [Uso PACMAN](#uso-pacman)
        - [Instalar Pacotes PACMAN](#instalar-pacotes-pacman)
        - [Desinstalar Pacotes PACMAN](#desinstalar-pacotes-pacman)
        - [Pesquisar Pacotes PACMAN](#pesquisar-pacotes-pacman)
    - [Sistemas Baseados em Debian](#sistemas-baseados-em-debian)
      - [Parâmetros APT](#parâmetros-apt)
      - [Uso APT](#uso-apt)
        - [Instalar Pacotes APT](#instalar-pacotes-apt)
        - [Desinstalar Pacotes APT](#desinstalar-pacotes-apt)
        - [Pesquisar Pacotes APT](#pesquisar-pacotes-apt)
    - [Sistemas Baseados em Red Hat Linux](#sistemas-baseados-em-red-hat-linux)
      - [Parâmetros DNF](#parâmetros-dnf)
      - [Uso DNF](#uso-dnf)
        - [Instalar Pacotes DNF](#instalar-pacotes-dnf)
        - [Desinstalar Pacotes DNF](#desinstalar-pacotes-dnf)
        - [Pesquisar Pacotes DNF](#pesquisar-pacotes-dnf)
  - [Programação **C**](#programação-c)
    - [Compilar](#compilar)
    - [Executar](#executar)
    - [Compilar e Executar](#compilar-e-executar)

## Atalhos

Atalho               | Uso
:-------------------:|:--------------------------------------------------------
`Ctrl` + `Alt` + `T` | Usado para abrir o Terminal
`Ctrl` + `C`         | Usado para cancelar operação em andamento no terminal
`Ctrl` + `L`         | Usado para limpar a tela do terminal (Comando **clear**)
`Ctrl` + `D`         | Usado para fazer **logout** ou fechar o terminal

## Links de Referência

- [Comandos Importantes Linux](https://www.devmedia.com.br/comandos-importantes-linux/23893)
- [30 Comandos Linux Que Todo Usuário Deve Conhecer](https://www.hostinger.com.br/tutoriais/comandos-linux)
- [Guia 500 Comandos Linux](https://www.linuxpro.com.br/dl/guia_500_comandos_Linux.pdf) - (Avançado)

## Instruções

Váriaveis serão identificadas com $ no inicio e no fim, onde essas deverão ser substituidas pelo nome do arquivo ou váriavel desejada.

*Ex.*:

- `$var1$` - Variável com nome ***var1***.
- `$arquivo$` - Variável que deve ser substituida pelo nome do arquivo.

## Comandos Básicos

Comando     |   Significado     |   Uso
:----------:|:-----------------:|:-----------
**clear**   |   Limpar  |   Usado para limpar a tela do terminal
**cd**      |  ***C**hange **D**irectory*<br>Trocar Diretório (Pasta) | Usado para trocar de pasta de trabalho
**pwd**     |  ***P**rint **W**orking **D**irectory*<br>Imprimir Diretório de Trabalho  |  Comando usado para saber o caminho completo da pasta de trabalho atual
**ls**      |   *<b>L</b>i<b>s</b>t*<br>Listar |   Usado para listar arquivos e diretórios dentro do diretório atual
**cat**     |   *<b>C</b>onc<b>at</b>enate*<br>Concatenar  |   Usado para que seja impresso na tela o conteúdo do arquivo desejado<br>*Ex.*: `cat $arquivo$`
**cp**      |   *<b>C</b>o<b>p</b>y*<br>Copiar  |   Usado para copiar um arquivo e colar em outro local<br>*Ex.*: `cp $caminhoOrigem$/$arquivoOrigem$ $caminhoDestino$/$arquivoDestino$`
**mv**      |   *<b>M</b>o<b>v</b>e*<br>Mover   |   Usado para mover um arquivo para um novo diretório<br>*Ex.*: `mv $caminhoOrigem$/$arquivoOrigem$ $caminhoDestino$/$arquivoDestino$`
**mkdir**   |   *<b>M</b>a<b>k</b>e **Dir**ectory*<br>Criar Diretório   |   Usado para criar um novo diretório (pasta)<br>*Ex.*: `mkdir $diretorio$`
**rm**      |   *<b>R</b>e<b>m</b>ove*<br>Remover/Apagar    |   Usado para remover/apagar arquivos<br>*Ex.*: `rm $arquivo$`
**rmdir**   |   *<b>R</b>e<b>m</b>ove **Dir**ectory*<br>Remover/Apagar Diretório    |   Comando usado para remover/apagar um diretório vazio<br>*Ex.*: `rmdir $diretorio$`
**touch**   |   Criar Arquivos  |   Usado para criar um arquivo em branco<br>*Ex.*: `touch $arquivo$`
**man**     |   ***Man**ual*    |   Usado para exibir o manual de uso de um determinado comando<br>*Ex.*: `man $comando$`
**sudo**    |   ***S**uper **U**ser **Do***<br>Fazer como Super Usuário |   Usado para executar comandos como Super Usuário (Administrador)<br>*Ex.*: `sudo $comando$`
**chmod**   |   ***Ch**ange **Mod**e*<br>Alterar Modo | Usado para configurar ou alterar permissões sobre um arquivo ou diretório

## Parâmetros

Parâmetros são usados para aumentar/definir quais funcionalidades de cada comando deseja que seja utilizado. Em geral os parâmetros são passados usando a forma `-$parametro$` ou `--$parametro$`

Um exemplo de parâmetro é o usado para remover diretórios (pastas) em que há conteúdos dentro dele, neste caso se usa o comando **rm** com os parâmetros:

- **r** - Recursivo (Apagar pasta e todo seu conteúdo)
- **f** - Forçar (Força que os arquivos sejam apagados)

***Obs.¹*** : Os parâmetros passados na forma `-$parametro$` podem ser concatenados em um só.  

***Ex.¹*** : Supondo que vamos passar os parâmetros *x y z* em um comando, podemos usar esses parâmetros de duas formas: `$comando$ -x -y -z` ou `$comando$ -xyz`  

***Obs.²*** : Os parâmetros passados na forma `--$parametro$` **não** podem ser concatenados em um só.  
Sendo usado então da seguinte forma: `rm -rf $diretorio$`

***Ex.²*** : Para alterar as permissões de um arquivo, tornando-o executável usa-se o comando `sudo chmod +x $nomeArquivo$`

## Multiplos Comandos

Para inserir/usar mais de um comando em apenas uma linha, para que seja executado de forma **sequêncial** basta que se use `;` ou `&&` para separar os comandos.

***Ex.***: Para executar os seguintes comandos: *comando1*, *comando2* e *comando3*, seguindo a sequência descrita, pode-se usar as seguintes formas:

- `$comando1$; $comando2$; $comando3$`
- `$comando1$ && $comando2$ && $comando3$`

## Instalar Programas

**Pacotes**: São chamados de pacotes os aplicativos, bibliotecas ou dependências de programas que serão instalados em Sistemas Linux.

**Repositórios**: Servidores onde o gerenciador de pacotes de cada Sistema Operacional (**SO**) busca se há uma versão do pacote desejado para que o mesmo seja instalado no sistema.

### Programas Baixados da Internet

Para instalar programas baixados da internet devemos nos atentar a alguns detalhes, um deles sendo a extensão do arquivo baixado.

Se a extensão (final do nome do arquivo) for:

Extensão    |   Método
:----------:|:--------
**.deb**    | Pacote de instalação para sistemas baseados em ***Debian***, devem ser instalados usando o gerenciador de pacotes `apt` ou `apt-get`
**.rpm**    | Pacote de instalação para sistemas baseados em ***RedHat***, devem ser instalados usando o gerenciador de pacotes `dnf` ou `yum`
**.sh**     | Instaladores escritos em ***ShellScript***, podem ser usados para instalar programas em basicamente qualquer distribuição *Linux*, para realizar<br> a instalação basta executar o comando: `sh $NomeDoArquivo$` ou `./$NomeDoArquivo$`<br><br>***Obs.¹:** Há a possibilidade deste tipo de instalador estar sem nenhuma extensão ao final do arquivo*<br>***Obs.²:** A execução através do método `./$NomeDoArquivo$` só é possível se o arquivo tiver a permissão de execução,<br> caso o arquivo não tenha esta permissão basta atribuir esta a ele através do comando: `sudo chmod +x $NomeDoArquivo$`*

### Sistemas Baseados em Arch Linux

Sistemas Operacionais baseados em *Arch Linux*:

- Manjaro Linux
- Arco Linux

O gerenciador de pacotes oficial de sistemas baseados em *Arch* é o `pacman`.  
Pode-se instalar programas usando outros gerenciadores de pacotes, na qual podem buscar programas na **AUR**, como por exemplo `yay` e `pamac`

***Obs.¹*** : Tanto o gerenciador de pacotes oficial `pacman` quanto o `yay` usam os mesmos parâmetros para instalação/atualização de pacotes, o gerenciandor `pamac` é voltado para uso em Interface Gráfica (**GUI**).

***Obs.²*** : O gerenciador de pacotes `pacman` deve ser usado com permissões de Super Usuário (**sudo**)

#### AUR

A **AUR** ou ***A**rch **U**ser **R**epository* (Repositório de Usuários do Arch Linux) é um repositório onde usuários/empresas podem publicar *scripts*/instaladores para aplicativos ou ports de aplicações (aplicativos portados de outros **SO**)

#### Parâmetros PACMAN

Os gerenciadores de pacote do *Arch* usam os seguintes parâmetros:

Parâmetro   |   Uso
:----------:|---------
**S**       |   Usado para instalar pacotes
**R**       |   Usado para remover/desinstalar pacotes
**Syu**     |   Usado para atualizar pacotes
**Ss**      |   Usado para pesquisar por **nome** e **descrição** de pacotes
**Si**      |   Usado para exibir informações detalhadas sobre o pacote
**Syyuu**   |   Usado para forçar sincronização dos repositórios e atualizar pacotes

#### Uso PACMAN

##### Instalar Pacotes PACMAN

- `sudo pacman -S $pacote$`
- `yay -S $pacote$`

Instalando mais de um pacote por vez:

- `sudo pacman -S $pacote1$ $pacote2$ $pacote3$`
- `yay -S $pacote1$ $pacote2$ $pacote3$`

##### Desinstalar Pacotes PACMAN

- `sudo pacman -R $pacote$`
- `yay -R $pacote$`

Desinstalando mais de um pacote por vez:

- `sudo pacman -R $pacote1$ $pacote2$ $pacote3$`
- `yay -R $pacote1$ $pacote2$ $pacote3$`

##### Pesquisar Pacotes PACMAN

- `sudo pacman -Ss $pacote$`
- `yay -Ss $pacote$`

### Sistemas Baseados em Debian

Sistemas Operacionais baseados em *Debian Linux*:

- Ubuntu Linux
- Linux Mint
- Elementary OS
- Raspibian

O gerenciador de pacotes oficial de sistemas baseados em *Debian* é o `apt` ou em versões mais antigas o `apt-get`.

Este gerenciador de pacotes pode ser udado para instalar pacotes baixados da internet com extensão (final) `.deb`

 ***Obs.***: O gerenciador de pacotes de **SO**s baseados em *Debian* precisam de permissões de Super Usuário (**sudo**) para serem executados

#### Parâmetros APT

Os gerenciadores de pacote do *Arch* usam os seguintes parâmetros:

Parâmetro   |   Uso
:----------:|---------
**install** |   Usado para instalar pacotes
**remove**  |   Usado para remover/desinstalar pacotes
**search**  |   Usado para pesquisar por **nome** e **descrição** de pacotes
**update**  |   Usado para atualizar pacotes
**upgrade** |   Usando para fazer o *upgrade* do sistema

#### Uso APT

##### Instalar Pacotes APT

- `sudo apt install $pacote$`
- `sudo apt-get install $pacote$`

Instalando mais de um pacote por vez:

- `sudo apt install $pacote1$ $pacote2$ $pacote3$`
- `sudo apt-get install $pacote1$ $pacote2$ $pacote3$`

##### Desinstalar Pacotes APT

- `sudo apt remove $pacote$`
- `sudo apt-get remove $pacote$`

Desinstalando mais de um pacote por vez:

- `sudo apt remove $pacote1$ $pacote2$ $pacote3$`
- `sudo apt-get $pacote1$ $pacote2$ $pacote3$`

##### Pesquisar Pacotes APT

- `sudo apt search $pacote$`
- `sudo apt-get search $pacote$`

### Sistemas Baseados em Red Hat Linux

Sistemas Operacionais baseados em *Red Hat Linux*:

- Fedora Linux
- CentOS

O gerenciador de pacotes oficial de sistemas baseados em *Red Hat* é o `yum` ou em versões mais novas (principalmente no *Fedora*) pode-se usar o `dnf`.

Este gerenciador de pacotes pode ser udado para instalar pacotes baixados da internet com extensão (final) `.rpm`

 ***Obs.***: O gerenciador de pacotes de **SO**s baseados em *Red Hat* precisam de permissões de Super Usuário (**sudo**) para serem executados

#### Parâmetros DNF

Os gerenciadores de pacote *RedHat* usam os seguintes parâmetros:

Parâmetro   |   Uso
:----------:|---------
**install** |   Usado para instalar pacotes
**remove**  |   Usado para remover/desinstalar pacotes
**search**  |   Usado para pesquisar por **nome** e **descrição** de pacotes
**update**  |   Usado para atualizar pacotes
**upgrade** |   Usando para fazer o *upgrade* do sistema

#### Uso DNF

##### Instalar Pacotes DNF

- `sudo dnf install $pacote$`
- `sudo yum install $pacote$`

Instalando mais de um pacote por vez:

- `sudo dnf install $pacote1$ $pacote2$ $pacote3$`
- `sudo yum install $pacote1$ $pacote2$ $pacote3$`

##### Desinstalar Pacotes DNF

- `sudo dnf remove $pacote$`
- `sudo yum remove $pacote$`

Desinstalando mais de um pacote por vez:

- `sudo dnf remove $pacote1$ $pacote2$ $pacote3$`
- `sudo yum $pacote1$ $pacote2$ $pacote3$`

##### Pesquisar Pacotes DNF

- `sudo dnf search $pacote$`
- `sudo yum search $pacote$`

## Programação **C**

### Compilar

Para compilar programas em **C** usa-se o comando `gcc` com o seguinte parâmetro:

- **o** - Nome do arquivo de saída/compilado

Sendo assim o comando usado para compilar programas em **C** é: `gcc $codigo$ -o $nomePrograma$`

### Executar

Para executar um programa **C** compilado basta usar o comando: `./$nomePrograma$`

### Compilar e Executar

Pode-se usar a forma mostrada na seção **Multicomandos** para que o código seja compilado e em seguida já executado, ficando então: `gcc $codigo$ -o $nomePrograma$; ./$nomePrograma$`
