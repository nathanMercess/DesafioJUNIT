1°) "Errors exist in required projects"

Classe JulgamentoPrisioneiro {
   int PENA_INOCENCIA = 0;
   int PENA_CONDENACAO_MUTUA = 5;
   int PENA_CONDENACAO_INDIVIDUAL = 10;
   int PENA_CONDENACAO_CUMPLICES = 1;

   int calculaPena(String respostaPrisioneiroA, String respostaPrisioneiroB) {
      se (respostaPrisioneiroA = “Culpado”) {
          se (respostaPrisioneiroB = “Culpado”) {
            retorna PENA_CONDENACAO_MUTUA;
          } senao {
                 retorna PENA_CONDENACAO_INDIVIDUAL;
                 }
       } senao {
                se (respostaPrisioneiroB = “Culpado”) {
                    retorna PENA_CONDENACAO_CUMPLICES;
                } senao {
                         retorna PENA_INOCENCIA;
                        }
                }
     }
}

# Test utilizado
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

	   int PENA_INOCENCIA = 13;
	   int PENA_CONDENACAO_MUTUA = 15;
	   int PENA_CONDENACAO_INDIVIDUAL = 10;
	   int PENA_CONDENACAO_CUMPLICES = 11;

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

3°) Testando parte B do primeiro IF, sucesso, segue o código de teste utilizado :

	@Test
	void testCalculaPena() {
		String t1 = "Culpado";
		String t2 = "Culpado";
		
		JulgamentoPrisioneiro julg = new JulgamentoPrisioneiro();
		int resultadoEsperado = 15; 
		int resultado = julg.calculaPena(t1, t2);
		assertEquals(resultadoEsperado, resultado);
	}
	
	@Test
	void ParteBdoPrimeiroIf() {
		String t1 = "Culpado";
		String t2 = "";
		
		JulgamentoPrisioneiro julg = new JulgamentoPrisioneiro();
		int resultadoEsperado = 10; 
		int resultado = julg.calculaPena(t1, t2);
		assertEquals(resultadoEsperado, resultado);
	}

4°) testando Else, sucesso, segue o código de teste utilizado :

	@Test
	void testCalculaPena() {
		String t1 = "Culpado";
		String t2 = "Culpado";
		
		JulgamentoPrisioneiro julg = new JulgamentoPrisioneiro();
		int resultadoEsperado = 15; 
		int resultado = julg.calculaPena(t1, t2);
		assertEquals(resultadoEsperado, resultado);
	}
	
	@Test
	void ParteBdoPrimeiroIf() {
		String t1 = "Culpado";
		String t2 = "";
		
		JulgamentoPrisioneiro julg = new JulgamentoPrisioneiro();
		int resultadoEsperado = 10; 
		int resultado = julg.calculaPena(t1, t2);
		assertEquals(resultadoEsperado, resultado);
	}
	
	@Test
	void TesteElsePena() {
		String t1 = "";
		String t2 = "Culpado";
		
		JulgamentoPrisioneiro julg = new JulgamentoPrisioneiro();
		int resultadoEsperado = 11; 
		int resultado = julg.calculaPena(t1, t2);
		assertEquals(resultadoEsperado, resultado);
	}
5°) testando elseParte, Sucesso, segue o código de teste utilizado : 

	@Test
	void testCalculaPena() {
		String t1 = "Culpado";
		String t2 = "Culpado";
		
		JulgamentoPrisioneiro julg = new JulgamentoPrisioneiro();
		int resultadoEsperado = 15; 
		int resultado = julg.calculaPena(t1, t2);
		assertEquals(resultadoEsperado, resultado);
	}
	
	@Test
	void ParteBdoPrimeiroIf() {
		String t1 = "Culpado";
		String t2 = "";
		
		JulgamentoPrisioneiro julg = new JulgamentoPrisioneiro();
		int resultadoEsperado = 10; 
		int resultado = julg.calculaPena(t1, t2);
		assertEquals(resultadoEsperado, resultado);
	}
	
	@Test
	void TesteElsePena() {
		String t1 = "";
		String t2 = "Culpado";
		
		JulgamentoPrisioneiro julg = new JulgamentoPrisioneiro();
		int resultadoEsperado = 11; 
		int resultado = julg.calculaPena(t1, t2);
		assertEquals(resultadoEsperado, resultado);
	}
	
	@Test
	void TesteElseParteBPena() {
		String t1 = "";
		String t2 = "";
		
		JulgamentoPrisioneiro julg = new JulgamentoPrisioneiro();
		int resultadoEsperado = 13; 
		int resultado = julg.calculaPena(t1, t2);
		assertEquals(resultadoEsperado, resultado);
	}
