# IA-atividade-java
Modificações do código java compartilhado em aula.
Calina Evelly//

1. Mudança nos carcteres do vetor declarado na váriavel cfgFim (linha 15 do código Main.java).
   Váriavel original: char[] cfgFim = {'1','2','3','4','5','6','7',' ','8'}; // OutOfMemory
   Váriavel modificada: char[] cfgFim = {'1','2','3','4','5','6','7','8',' '}; // OutOfMemory
   Mudança observada: Nenhuma, o comentário // OutOfMemory deixado indica um erro de falta de memória.

2. Mudança no trecho de código que define o tipo de busca, trocando a Busca em Largura por Busca em Profundidade (linha 28-19).
   
   Trecho original:
    		                  BuscaCega busca = new BuscaEmLargura();
		                //    BuscaCega busca = new BuscaEmProfundidade();
   	                    //	  BuscaCega busca = new BuscaEmProfundidadeLimitada(null, null, 16);
   
   Trecho modificado:
                       //	BuscaCega busca = new BuscaEmLargura();
		                    BuscaCega busca = new BuscaEmProfundidade();
                      //	BuscaCega busca = new BuscaEmProfundidadeLimitada(null, null, 16);
   
   Mudança observada: O resultado original é o Puzzle, do level 0 a 9. Quando a modificação é feita, o resultado se torna
   
Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
	at java.base/java.util.ArrayList.grow(ArrayList.java:239)
	at java.base/java.util.ArrayList.grow(ArrayList.java:244)
	at java.base/java.util.ArrayList.add(ArrayList.java:483)
	at java.base/java.util.ArrayList.add(ArrayList.java:496)
	at espacoDeEstados.Puzzle8.getSucessores(Puzzle8.java:275)
	at estrategiasDeBusca.cega.BuscaEmProfundidade.buscar(BuscaEmProfundidade.java:52)
	at Main.main(Main.java:38)

Que é um erro de falta de memória que significa que o Eclipse tentou alocar mais memória do que o máximo que a Máquina Virtual Java tem disponível.
