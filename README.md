
## Instalação:

Uso: `./install.sh [OPÇÕES...]`

```
  -t, --theme Variantes do tema de fundo [forest|mojave|mountain|wave] (o padrão é forest)
  -p, --type Variantes do estilo do tema [window|float|sharp|blur] (o padrão é janela)
  -i, --side Lado da exibição da imagem [left|right] (o padrão é esquerda)
  -c, --color Variantes da cor de fundo [dark|light] (o padrão é escuro)
  -s, --screen Variantes da exibição da tela [1080p|2k|4k] (o padrão é 1080p)
  -l, --logo Mostrar um logotipo na imagem [default|system] (padrão: o logo mountain)
  -r, --remove Remover/Desinstalar tema (deve adicionar opções de tema, o padrão é Elegant-forest-window-left-dark)
  -b, --boot Instalar tema em '/boot/grub' ou '/boot/grub2'
  -h, --help Mostrar esta ajuda
```

_Se nenhuma opção for usada, uma `caixa de diálogo` de interface de usuário será exibida_

### Exemplos:
 - Instalar tema mountain em dispositivo de exibição 2k:

```sh
sudo ./install.sh -t mountain -s 2k
```

 - Instalar tema wave em /boot/grub/themes:

```sh
sudo ./install.sh -b -t wave
```

 - Desinstalar tema mountain:

```sh
sudo ./install.sh -r -t mountain
```

## Problemas/ajustes:

### Corrigindo resolução de exibição:

 - Na tela do grub, pressione `c` para entrar na linha de comando
 - Digite `vbeinfo` ou `videoinfo` para verificar as resoluções disponíveis
 - Abrir `/etc/default/grub` e edite `GRUB_GFXMODE=[height]x[width]x32` para corresponder à sua resolução
 - Finalmente, execute `grub-mkconfig -o /boot/grub/grub.cfg` para atualizar sua configuração do grub

### Configurando um plano de fundo personalizado:

 - Certifique-se de ter `imagemagick` instalado ou pelo menos algo que forneça `convert`
 - Encontre a resolução da sua tela e certifique-se de que seu plano de fundo corresponda à resolução
 - 1920x1080 >> 1080p
 - 2560x1440 >> 2k
 - 3840x2160 >> 4k
 - Coloque seu plano de fundo personalizado dentro da raiz do projeto e nomeie-o `background.jpg`
 - Execute o instalador normalmente, mas com -s `[SUA_RESOLUÇÃO]` e -t `[TEMA]` e -i `[ÍCONE]`
 - Certifique-se de para substituir `[SUA_RESOLUÇÃO]` pela sua resolução e `[TEMA]` pelo tema

## Contribuindo:
 - Se você fez alterações nos ícones ou adicionou um novo:
 - Exclua o ícone existente, se houver um
 - Execute `cd assets; ./render-all.sh`
 - Crie uma solicitação de pull do seu branch ou fork
 - Se ocorrer algum problema, informe-o na página [issue](issues)

## Visualização:
![preview-01](preview-01.jpg?raw=true)
![preview-02](preview-02.jpg?raw=true)
![preview-03](preview-03.jpg?raw=true)
![preview-04](preview-04.jpg?raw=true)

## Documentos

[Referência do tema Grub2](https://github.com/vinceliuice/Elegant-grub2-themes)

