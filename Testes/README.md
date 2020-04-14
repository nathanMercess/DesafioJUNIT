1°) "Errors exist in required projects"
	
	@Test
	void testCalculaPena() {
		String t1 = "Culpado";
		String t2 = "Culpado";
		
		JulgamentoPrisioneiro julg = new JulgamentoPrisioneiro();
		int resultadoEsperado = 5; 
		int resultado = julg.calculaPena(t1, t2);
		assertEquals(resultadoEsperado, resultado);
	}
2°) Sucesso! após alteração no trecho a seguir: 
	public class JulgamentoPrisioneiro {

	   int PENA_INOCENCIA = 0;
	   int PENA_CONDENACAO_MUTUA = 5;
	   int PENA_CONDENACAO_INDIVIDUAL = 10;
	   int PENA_CONDENACAO_CUMPLICES = 1;

	   int calculaPena(String respostaPrisioneiroA, String respostaPrisioneiroB) {
	      if (respostaPrisioneiroA == "Culpado") {
	          if (respostaPrisioneiroB == "Culpado") {
	            return PENA_CONDENACAO_MUTUA;
	          } else {
	        	  return PENA_CONDENACAO_INDIVIDUAL;
	                 }
	       } else {
	                if (respostaPrisioneiroB == "Culpado") {
	                	return PENA_CONDENACAO_CUMPLICES;
	                } else {
	                	return PENA_INOCENCIA;
	                        }
	                }
	     }
}
