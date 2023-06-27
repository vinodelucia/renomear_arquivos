# renomear_arquivos
Em resumo, o código lê um arquivo Excel contendo informações sobre arquivos a serem renomeados, obtém os nomes antigos e os novos nomes dos arquivos a partir do DataFrame e realiza a renomeação dos arquivos no diretório especificado.

O código apresentado realiza uma análise de um DataFrame utilizando a biblioteca Pandas e renomeia arquivos em um diretório utilizando a biblioteca os do Python. Vamos analisar linha por linha:

import pandas as pd: Importa a biblioteca Pandas, que é amplamente utilizada para manipulação e análise de dados.

import os: Importa a biblioteca os, que fornece funções para interagir com o sistema operacional, incluindo operações em arquivos e diretórios.

print(os.getcwd()): Exibe o diretório de trabalho atual, que é o diretório no qual o código está sendo executado.

os.chdir('C:\\Users\\Correção\\Pictures\\100CANON'): Altera o diretório de trabalho atual para o caminho especificado. Neste caso, o diretório é definido como 'C:\\Users\\Correção\\Pictures\\100CANON'.

df = pd.read_excel('nomes_arquivos.xlsx', sheet_name='Sheet1'): Lê um arquivo Excel chamado 'nomes_arquivos.xlsx' e carrega os dados em um DataFrame do Pandas. O parâmetro sheet_name='Sheet1' indica que os dados devem ser lidos da planilha chamada 'Sheet1'.

folder_path = 'C:\\Users\\Correção\\Pictures\\100CANON': Define o caminho da pasta onde estão localizados os arquivos que serão renomeados.

O loop for i, row in df.iterrows(): itera sobre cada linha do DataFrame df, onde i representa o índice da linha e row é a série que contém os valores da linha.

old_filename = str(row['Nome antigo']) e new_filename = str(row['Novo nome']): Obtém os valores das colunas 'Nome antigo' e 'Novo nome' da linha atual do DataFrame e os converte para strings.

os.rename(os.path.join(folder_path, old_filename), os.path.join(folder_path, new_filename)): Renomeia o arquivo antigo para o novo nome. A função os.path.join() é usada para concatenar o caminho da pasta folder_path com os nomes dos arquivos.

print('Renomeação concluída com sucesso!'): Exibe uma mensagem indicando que a renomeação dos arquivos foi concluída com sucesso.
