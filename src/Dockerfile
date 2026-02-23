# Usa imagem oficial do Node 20.11.0
FROM node:20.11.0

# Define diretório de trabalho dentro do container, é TIPO um cd pra trocar pasta no Linux, a partir daqui, tudo feito no container será feito na pasta /app, até outro comando workdir ser feito
WORKDIR /app

# Copia apenas os arquivos de dependência pra dentro do workdi
# Isso permite cachear a etapa do npm install
COPY package*.json ./

# Instala dependências
RUN npm install

# Copia o restante do código da aplicação, do meu computaodr, pro diretorio do container (que agora é o /app definido no workdir)
COPY . .

# Informa que a aplicação roda na porta 8080
EXPOSE 8080

# Comando padrão ao iniciar o container
CMD [ "node", "server.js" ]