programa
{
	inclua biblioteca Graficos --> g
	inclua biblioteca Teclado --> t
	inclua biblioteca Util --> u

	const inteiro largura = 600, altura = 600
	logico choque = falso, permite_sorteio = verdadeiro
	funcao inicio()
	{
		cria_mesa()
		enquanto(verdadeiro)
		{
			choque = falso
			desenhar_mesa()
			desenhar_cobra()
			se(permite_sorteio == verdadeiro)
			{
				sorteia_cord_comida(50, 600)
			}
			desenha_comida()
			le_direcao()
			movimentar_cobra()
			confere_se_bateu()
			se(choque == verdadeiro)
			{
				desenha_tela_derrota()
			}

			g.renderizar()
			u.aguarde(10)
		}
	}
	funcao cria_mesa()
	{
		g.iniciar_modo_grafico(verdadeiro)
		g.definir_dimensoes_janela(largura, altura)
		g.definir_titulo_janela("jogo da cobra, simples")
	}
	funcao desenhar_mesa()
	{
		g.definir_cor(g.COR_AZUL)
		g.limpar()
	}
	inteiro X = 250, Y = 250
	funcao desenhar_cobra()
	{
		g.definir_cor(g.COR_PRETO)
		g.desenhar_retangulo(X, Y, 50, 50, verdadeiro, verdadeiro)
	}
	inteiro cord_X_comida, cord_Y_comida
	funcao sorteia_cord_comida(inteiro min, inteiro max)	
	{
		cord_X_comida = u.sorteia(min, max)
		cord_Y_comida = u.sorteia(min, max)
		permite_sorteio = falso
	}
	funcao desenha_comida()
	{		
		g.definir_cor(g.COR_AMARELO)
		g.desenhar_retangulo(cord_X_comida, cord_Y_comida, 25, 25, verdadeiro, verdadeiro)		
	}
	logico movimento_X_direita = falso, movimento_X_esquerda = falso, movimento_Y_acima  = falso, movimento_Y_abaixo = falso
	funcao le_direcao()
	{
		se(t.tecla_pressionada(t.TECLA_SETA_DIREITA))
		{
			movimento_X_direita = verdadeiro

			movimento_X_esquerda = falso
			movimento_Y_acima  = falso
			movimento_Y_abaixo = falso
		}
		se(t.tecla_pressionada(t.TECLA_SETA_ESQUERDA))
		{
			movimento_X_esquerda = verdadeiro

			movimento_X_direita = falso
			movimento_Y_acima  = falso
			movimento_Y_abaixo = falso
		}
		se(t.tecla_pressionada(t.TECLA_SETA_ACIMA))
		{
			movimento_Y_acima = verdadeiro

			movimento_X_direita = falso
			movimento_X_esquerda = falso
			movimento_Y_abaixo = falso
		}
		se(t.tecla_pressionada(t.TECLA_SETA_ABAIXO))
		{
			movimento_Y_abaixo = verdadeiro

			movimento_X_direita = falso
			movimento_X_esquerda = falso
			movimento_Y_acima  = falso
		}
	}
	funcao movimentar_cobra()
	{
		se(movimento_X_direita == verdadeiro)
		{
			X = X + 3
		}
		se(movimento_X_esquerda == verdadeiro)
		{
			X = X - 3
		}
		se(movimento_Y_acima == verdadeiro)
		{
			Y = Y - 3
		}
		se(movimento_Y_abaixo == verdadeiro)
		{
			Y = Y + 3
		}
	}
	funcao confere_se_bateu()
	{
		se((X >= cord_X_comida-20) e (X <= cord_X_comida+20))
		{
			se((Y >= cord_Y_comida-20) e (Y <= cord_Y_comida+20))
			{
				choque = verdadeiro
			}
		}
	}
	funcao desenha_tela_derrota()
	{
		g.definir_cor(g.COR_VERMELHO)
		g.definir_tamanho_texto(40.0)
		g.desenhar_texto(100, 400, "Você perdeu!")
		
		g.renderizar()
		u.aguarde(500)
		permite_sorteio = verdadeiro
	}
}
