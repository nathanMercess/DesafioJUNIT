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
