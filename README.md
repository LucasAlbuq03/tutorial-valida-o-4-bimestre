# Tutorial Validação 4º Bimestre

## Em um controlador como o que construímos, como garantir que somente requisições válidas serão repassadas ao banco de dados?

Um protocolo é um conjunto de regras para comunicação entre dois computadores. HTTP é um protocolo textual sem estado. 

Nem o servidor nem o cliente lembram de comunicações anteriores. Por exemplo, confiando apenas no HTTP, um servidor não consegue se lembrar de uma senha digitada ou da etapa em que você está em uma transação. 

O HTTP fornece regras claras sobre como um cliente e um servidor se comunicam. Abordaremos o próprio HTTP em um artigo técnico mais adiante. 

Somente clientes podem fazer requisições HTTP, e somente para servidores. Servidores podem apenas responder a uma requisição HTTP dos clientes.
Quando fizer a requisição de um arquivo via HTTP, os clientes devem fornecer a URL do arquivo.
O servidor web deve responder todas as requisições HTTP, mesmo que seja com uma mensagem de erro. 
Em um servidor web, o servidor HTTP é responsável por processar e responder as requisições recebidas. 
Ao receber uma requisição, um servidor HTTP primeiramente confirma se a URL requisitada corresponde ao arquivo existente.
Se confirmar, o servidor web envia o conteúdo do arquivo de volta ao navegador. Senão, o servidor de aplicações cria o arquivo necessário. 
ou seja quando não for possível enviar requisições validas, aparecera uma mensagem de erro na tela do navegador  e isso faz com que o Banco de dados (servidor)só receba requisições validas.

## Como responder ao usuário em caso de uma entrada incorreta?

Quando o usuario envia algum tipo de dados para o servidor e ele retorna a resposta que seus dados estão errados ou contém algum tipo de erro. 

Como já sabemos, ao acessar um servidor HTTP, recebemos divesas respostas de acordo com as entradas do usuario no servidor. 

Quando o usuario cometer a entrada errada, o servidor retornará: "using 404". No caso porque não encontrou o caminho, página, documento ou destino que não existe ou que aconteceu um erro de tranferência de dados.

Ao acontecer uma entrada incorreta, o 409 pode ser uma opção bem interessante de comunicar ao usuario que a entrada foi incorreta. O 409 retornará: "A solicitação não pôde ser concluída devido a um conflito com o estado atual do recurso de destino. Esse código é usado em situações em que o usuário pode resolver o conflito e reenviar a solicitação." Por meio de uma API criando uma string única no banco de dados, mais antes verificar se ainda estará no banco de dados. 

Se estiver retornar: "Error: The string is already in the database", 409.

Por nossas fontes de pesquisas, essa poderia ser uma forma adequada para quando a passagem de dados for incorreta.
