Resumo do problema:
Este projeto aborda o agendamento semanal de aulas para um dataset com três turmas do ensino superior. Cada unidade curricular precisa de duas sessões distribuídas por blocos horários compatíveis com a disponibilidade dos docentes e com a capacidade das salas, físicas ou virtuais. O objetivo é encontrar um horário viável que satisfaça todas as restrições obrigatórias, como ausência de sobreposições, limite diário de aulas e salas dedicadas, reduzindo ao mesmo tempo penalizações associadas a preferências como distribuir sessões por dias distintos ou evitar trocas frequentes de sala.

Tecnologias utilizadas:
Python para executar os algoritmos de satisfação de restrições, Jupyter Notebook (ficheiro Projeto_1_IA.ipynb) para documentação e experimentação e a biblioteca python-constraint, em particular o solver MinConflictsSolver para procura local.

Requisitos de ambiente e configuração:
1) Instale o Python 3.10 ou superior.
2) Abra o ficheiro Projeto_1_IA.ipynb na interface do Visual Studio Code ou PyCharm e execute as células sequencialmente através de Run All ou Shift+Enter.

Opcionalmente, também pode carregar e executar o ficheiro Projeto_1_IA.ipynb diretamente no Google Colab.

Execução e interpretação dos resultados:
As primeiras células carregam bibliotecas e constroem os domínios das variáveis UCxx_1 e UCxx_2. Na secção Procura da melhor solução, o MinConflictsSolver é executado múltiplas vezes com sementes determinísticas. A melhor solução encontrada, a com menos penalizações, fica armazenada e é apresentada nas secções seguintes. A secção Visualização do horário resultante devolve uma vista do horário por dia e bloco e outra ordenada pelos blocos. Uma penalização igual a 0 indica que todas as restrições duras e preferências suaves foram satisfeitas.

Ajuste do dataset:
As estruturas principais encontram-se na secção Mapas entre turmas, docentes e salas do notebook. Pode personalizar o problema editando os dicionários courseClasses (associação de turmas t01, t02 e t03 às unidades curriculares), classLecturers (docente responsável por cada unidade), classRooms (salas obrigatórias), timeRestrictions (blocos proibidos para docentes), daysBlocks (organização dos blocos B01 a B20 por dia útil) e os conjuntos onlineLessons e physicalRooms. Depois de qualquer alteração deve voltar a executar todas as células para gerar um novo horário.

Notas para possíveis melhorias:
Utilizar um algoritmo de backtracking da biblioteca python-constraint rapidamente tornou-se impossível, devido ao tamanho do dataset, demorava horas para encontrar uma única solução. Tivemos de recorrer a um algoritmo de procura local, MinConflictsSolver. Para uma possível melhoria, seria no próximo projeto utilizar as ferramentas OR-Tools da Google, que são mais rápidas e poderão tornar viável o uso de algoritmos de backtracking.

Repositório:
Link para o repositório original https://github.com/AnyTng/IA25_P01_G10
