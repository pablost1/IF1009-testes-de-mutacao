# IF1009-testes-de-mutacao

Teste de Mutação em Projetos Reais: Avaliação da Eficácia de Testes

Este estudo explora o teste de mutação, uma técnica avançada para avaliar a eficácia de testes de software, aplicando-a ao framework Express por meio da ferramenta Stryker Mutator. A escolha desse caso de uso considera dois critérios principais:
Adequação técnica da equipe: Todos os membros possuem domínio em JavaScript, linguagem na qual tanto o Express quanto o Stryker são desenvolvidos.
Perfil do projeto: O Express, como um framework amplamente adotado em Node.js, oferece um ecossistema robusto para validar a eficácia do teste de mutação em cenários reais.
Essa combinação — JavaScript como linguagem base, Express como projeto-alvo e Stryker como ferramenta de mutação — garantiu não apenas a viabilidade técnica, mas também a relevância prática da análise.

4 Resultados
Esta seção apresenta uma análise detalhada dos dados coletados durante a execução dos testes de mutação aplicados às diferentes versões do Express.js. Os resultados foram organizados em gráficos que comparam métricas-chave para avaliar a eficácia dos testes, como a taxa de sobrevivência de mutantes, o mutation score e o número de mutantes eliminados em cada versão do framework.
4.1 Total de Mutantes Criados
O primeiro resultado obtido foi o total de mutantes gerados, uma vez que esse dado fornece uma visão geral do cenário de mutação e simplifica a interpretação dos gráficos subsequentes, tanto de mutantes sobreviventes quanto de mutantes detectados. O gráfico correspondente é apresentado abaixo:
![image](https://github.com/user-attachments/assets/dce090e9-2bb4-4cd8-b913-1e4f682cfc6a)

Com base nos dados, observa-se que, a partir da versão 5.0.0, houve uma redução significativa no número de mutantes gerados. Esse comportamento está diretamente associado à diminuição da quantidade de arquivos utilizados pelo projeto nessa versão. Como consequência, esse fenômeno afetará os demais resultados analisados. Contudo, mesmo com essa tendência, ainda é possível identificar variações relevantes entre as três versões da série 4.21.x, nas quais se nota uma leve diminuição progressiva na quantidade de mutantes.
4.2 Total de Mutantes Sobreviventes(Survived)
A coleta de dados sobre mutantes sobreviventes é de grande relevância, pois, por meio dela, é possível avaliar efetivamente o nível de vulnerabilidade da bateria de testes do projeto analisado. Essa é talvez a informação mais importante, já que permite identificar e corrigir tais vulnerabilidades. Os dados podem ser visualizados no gráfico a seguir: 
![image](https://github.com/user-attachments/assets/e7eb2674-7c00-447e-931a-eb4de3cc7ff1)

Analisando os dados da versão 4.21.0 para a 4.21.1, observa-se uma leve redução no número de mutantes sobreviventes. Entretanto, na versão subsequente, esse número aumenta consideravelmente. Esse comportamento é, de certa forma, preocupante, pois indica que os testes estão se tornando progressivamente mais vulneráveis. Contudo, com o lançamento da nova versão 5.0.0, o Express apresenta uma queda significativa na quantidade de mutantes sobreviventes. Além disso, na versão 5.0.1, os dados permanecem próximos aos da versão anterior.

4.3 Total de Mutantes Eliminados(Killed)
De outra perspectiva, a coleta de dados sobre mutantes eliminados também é fundamental, pois demonstra a eficiência da bateria de testes na identificação efetiva de falhas. Em contraste com os dados de mutantes sobreviventes, essas métricas destacam os pontos fortes do código, permitindo reforçar práticas que elevem seu desempenho. O gráfico abaixo ilustram essas informações:
![image](https://github.com/user-attachments/assets/307d7887-733b-4e8e-9b64-597e9716dc02)

Da versão 4.21.0 à versão 4.21.2, observa-se uma queda significativa na identificação de mutantes. Esse dado evidencia o declínio na eficácia dos testes do projeto. Contudo, a partir da versão 5.0.0, mesmo com uma redução no tamanho do código, o conjunto de testes registrou um aumento expressivo na detecção de mutantes.

4.4 Mutation Score de Cada Versão
O mutation score é justamente a métrica que avalia a quantidade de testes com a quantidade de mutantes sobreviventes e eliminados. Essa métrica oferece uma visão clara do panorama geral da qualidade dos testes analisados. Os resultados podem ser observados no gráfico abaixo:
![image](https://github.com/user-attachments/assets/1fa94819-2cdf-4e92-971f-5f3e2a2469d9)

O mutation score evidencia que, apesar das flutuações entre mutantes sobreviventes e mutantes eliminados, a situação geral da bateria de testes permaneceu praticamente a mesma. Contudo, nos dados posteriores, será possível observar que, em arquivos críticos do projeto, houve mudanças significativas. Assim, embora haja pouca variação no geral, essa flutuação ocorre justamente em arquivos de grande impacto para o projeto.

4.5 Evolução dos Mutantes Sobreviventes(Survived) nos Arquivos Principais
A partir deste ponto, o que será analisado é especificamente a evolução dos seis arquivos principais do Express: application.js, express.js, request.js, response.js, utils.js e view.js.
Em continuidade à sequência lógica, é fundamental examinar o histórico de mutantes sobreviventes. Assim como destacado na Seção 4.2, esses dados são essenciais não apenas para identificar vulnerabilidades na bateria de testes, mas também para revelar tendências de redução ou aumento dessas fragilidades ao longo do tempo.
Essas informações estão representadas graficamente abaixo:
![image](https://github.com/user-attachments/assets/85a88365-1c93-458a-99ac-6d84616beb54)

Com base nesses dados, é possível identificar que, na versão 4.21.2, o arquivo response.js permitiu a passagem de uma quantidade maior de mutantes, atingindo cerca de sessenta casos. No entanto, com exceção do application.js, a redução no número de mutantes sobreviventes foi bastante expressiva. Esse cenário reforça a evolução que se consolida especificamente a partir da versão 5.0.0.

4.6 Evolução dos Mutantes Eliminados(Killed) nos Arquivos Principais
Em contraste com os dados da seção 4.5, os dados da evolução dos mutantes eliminados mostram justamente a tendência do aumento ou diminuição da efetividade dos testes em detectar falhas. Isso é de suma importância para que se reforce práticas que melhorem o desempenho e se repense práticas que reduzem o desempenho dos testes. O gráfico abaixo ilustram essas informações:
![image](https://github.com/user-attachments/assets/cf740858-0b30-49e2-93f5-cbd0d80a9a51)

De acordo com tais dados, é possível notar que, com exceção do response.js, todos os arquivos mantiveram a quantidade de mutantes eliminados. Em contrapartida, o response.js teve um declínio considerável de mutantes mortos a partir da versão 5.0.0. 

4.7 Evolução dos Mutation Score nos Arquivos Principais
Por fim, a evolução do mutation score nos arquivos principais é de suma importância. Isso porque tais dados contrastam com os dados coletados na seção 4.4, justamente saindo da esfera do geral e indo para esfera do específico. Os dados podem ser visualizados no gráfico a seguir: 
![image](https://github.com/user-attachments/assets/5fe960a1-282f-46fc-ac8a-4c063f5883e6)

Os dados revelam que o mutation score é ascendente em todos os arquivos, com exceção somente do response.js que possui o comportamento inverso e decresce ao longo do tempo.
