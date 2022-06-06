# PPTSL
import java.util.Random;
import java.util.Scanner;

public class Pedra {

	static Scanner in = new Scanner(System.in);
	
	static Random rdm = new Random();
	
	 static final byte[][] REGRAS = {
				{0,-1,1,1,-1},
				{1,0,-1,-1,1},
				{-1,1,0,1,-1},
				{-1,1,-1,0,1},
				{1,-1,1,-1,0}
		};
	
	 static final String[] opcoes = {"Pedra","Papel","Tesoura", "Lagarto", "Spock"};
	 
	static final byte GANHOU = 1;
	static final byte EMPATOU = 0;
	static final byte PERDEU = -1;
	
	static int pcOpcao() {
		
		return rdm.nextInt(REGRAS.length);
			
	}
	
	static int opcaoJogador() {
		
		System.out.println("[0] Pedra");
		System.out.println("[1] Papel");
		System.out.println("[2] Tesoura");
		System.out.println("[3] Lagarto");
		System.out.println("[4] Spock");
		System.out.println();
		System.out.println("Opção: ");
		
			return in.nextInt();
	}
			
	public static void main(String[] args) {
		
		int jogador = opcaoJogador();
		int computador = pcOpcao();
		
		System.out.printf("Jogador selecionou: %s", opcoes[jogador]);
		System.out.println();
		System.out.printf("Computador selecionou: %s", opcoes[computador]);
		System.out.println();
		
		
		if(REGRAS[jogador][computador] == GANHOU) {
			System.out.println("O Jogador venceu!");
			
		} else if(REGRAS[jogador][computador] == EMPATOU) {
			System.out.println("O Jogo empatou!");
			
		} else if(REGRAS[jogador][computador] == PERDEU) {
			System.out.println("O Computador venceu!");
			
		}
		
		

	}

}
