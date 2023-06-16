package devtheshowgame;
import java.util.Scanner;
import java.util.ArrayList;
public class DevTheShowGame {

   public static void main(String[] args) {
    System.out.println("Bem vindo ao DevShow!!!");
    
   Scanner scanner = new Scanner(System.in);
        Opcoes opcoes = new Opcoes("Iniciar", "Devs", "Sair");

        boolean sair = false;

        while (!sair) {
            System.out.println("=== Menu ===");
            System.out.println("1. " + opcoes.getIniciar());
            System.out.println("2. " + opcoes.getDevs());
            System.out.println("3. " + opcoes.getSair());
            System.out.println("Escolha uma opcao:");

            int escolha = scanner.nextInt();
            scanner.nextLine(); 

            switch (escolha) {
                case 1:
                    System.out.println("Opcao 'Iniciar' selecionada.");
                    sair = true;
                    break;
                case 2:
                    String link1 = "https://github.com/MiguelPinheiro2409";
                    String link2 = "https://github.com/cauahenriquearaujo";
                    System.out.println("Opcao 'Devs' selecionada.");
                    System.out.println("__________________________________________________________________");
                    System.out.println("Miguel:");
                    System.out.println("-Programador");
                    System.out.println("-Revisor");
                    System.out.println("Github: " + link1);
                    System.out.println("__________________________________________________________________");
                    System.out.println("Caua:");
                    System.out.println("-Redator");
                    System.out.println("-Modelador");
                    System.out.println("Github: " + link2);
                    System.out.println("__________________________________________________________________");
                    
                    boolean voltarMenu = false;
                    while (!voltarMenu) {
                        System.out.println("Deseja voltar para o menu? (S/N)");
                        String resposta = scanner.nextLine();

                        if (resposta.equalsIgnoreCase("S")) {
                            voltarMenu = true;
                        } else if (resposta.equalsIgnoreCase("N")) {
                            System.out.println("Encerrando o programa...");
                            return;
                            
                        } else {
                            System.out.println("Resposta invalida. Digite 'S' para voltar"
                                    + " ao menu ou 'N' para encerrar o programa.");
                        }
                    }
                    break;
                case 3:
                    System.out.println("Opcao 'Sair' selecionada. Encerrando o programa...");
                    sair = true;
                    return;
                default:
                    System.out.println("Opcao invalida. Tente novamente.");
                    break;
            }

            if (!sair) {
                System.out.println("Pressione Enter para continuar...");
                scanner.nextLine();
            }
        }

     //começo do jogo
    System.out.println("Jogador 1, escolha um personagem de 1 a 3:");
    System.out.println("__________________________________________________________________");
    
    
    //Cria personagens
    Personagem perso1 = new Personagem("1)Dio", 0, 10);
    Personagem perso2 = new Personagem("2)Koichi", 0, 10);
    Personagem perso3 = new Personagem("3)Lisa", 0, 10);
    
    
   
    ArrayList<Personagem> persona = new ArrayList<Personagem>();
    persona.add(perso1);
    persona.add(perso2);
    persona.add(perso3);
    Scanner scan = new Scanner(System.in);
   
    
    for(Personagem personagem: persona){
        System.out.println(personagem.getNome());   
    }
    
   //escolha de personagem 1
    boolean perso1Selecionado = false;
    boolean perso2Selecionado = false;
    boolean perso3Selecionado = false;

    boolean personagemCorreto = false;

    while (!personagemCorreto) {
        int esc;
        esc = scan.nextInt();

        if (esc == 1) {
        personagemCorreto = true;
        System.out.println("Jogador 1 escolheu: " + perso1.getNome());
        perso1Selecionado = true;
       } else if (esc == 2) { 
        personagemCorreto = true;
        System.out.println("Jogador 1 escolheu: " + perso2.getNome());
        perso2Selecionado = true;
       } else if (esc == 3) {
        personagemCorreto = true;
        System.out.println("Jogador 1 escolheu: " + perso3.getNome());
        perso3Selecionado = true;
       } else {
        System.out.println("Opcao invalida. Selecione novamente.\n");
       }
      }

    //Escolha personagem 2
    System.out.println("__________________________________________________________________");
    System.out.println("Jogador 2, escolha um personagem de 1 a 3:");

    for (Personagem personagem : persona) {
    System.out.println(personagem.getNome());
    }
    
    boolean personagemCorreto2 = false;

    while (!personagemCorreto2) {
        int esc_2;
        esc_2 = scan.nextInt();

     if (esc_2 == 1 && !perso1Selecionado) {
        personagemCorreto2 = true;
        System.out.println("jogador 2 escolheu: " + perso1.getNome());
        perso1Selecionado = true;
     } else if (esc_2 == 2 && !perso2Selecionado) {
        personagemCorreto2 = true;
        System.out.println("jogador 2 escolheu: " + perso2.getNome());
        perso2Selecionado = true;
     } else if (esc_2 == 3 && !perso3Selecionado) {
        personagemCorreto2 = true;
        System.out.println("jogador 2 escolheu: " + perso3.getNome());
        perso3Selecionado = true;
     } else {
       System.out.println("Opcao invalida ou personagem ja selecionado. Selecione novamente.\n");
     }
    }
       System.out.println("Certo, vamos comecar.");
       System.out.println("__________________________________________________________________");
       
       //criar perguntas
      Pergunta perg1 = new Pergunta("Quais sao os valores possiveis de um tipo de "
              + "dados boolean em Java", "1)bom/ruim , 2)sim/nao , 3)verdadeiro/falso ");
      
      Pergunta perg2 = new Pergunta("Qual operador eh usado para testar se os dois lados"
              + " de uma expressao boolean sao iguais?", "1)==, 2)<= , 3)=");
      
      Pergunta perg3 = new Pergunta("Qual eh a maneira correta de converter um tipo long"
              + " (longo) em um tipo int (inteiro)?",
              "1)int longToInt = (int)20L; , 2)int longToInt = int 20L; , 3)int longToInt = 20L(int); ");
      
      Pergunta perg4 = new Pergunta("Dada a instrucao de importacao: import java.awt.font.TextLayout;"
              + ", qual eh o nome do pacote?", "1)awt.font , 2)java.awt.font , 3)java.awt ");
      
      Pergunta perg5 = new Pergunta("Qual eh o risco de usar nomes de classe totalmente qualificados durante a importacao?"
              , "1)A legibilidade do codigo diminui. , 2)O uso da memoria aumenta. , 3)O desempenho do codigo diminui ");
      
      Pergunta perg6 = new Pergunta("Quais valores sao retornados pelo metodo nextBoolean();?",
              "1)Verdadeiro ou falso. , 2)Retorna o próximo valor. , 3)Um valor inteiro. ");
      
      Pergunta perg7 = new Pergunta("Voce precisa gerar valores inteiros aleatorios entre 0 e 80 "
              + "(incluindo 0 e 80). Que instrucao voce deve usar?",
              "1)nextInt(81); , 2)nextInt(80); , 3)nextInt(0-79); ");
      
      Pergunta perg8 = new Pergunta("Qual classe eh usada para gerar numeros aleatorios?",
              "1)Double , 2)Random , 3)Number ");
      
      Pergunta perg9 = new Pergunta("O que nao eh usado para percorrer uma Lista de Matrizes?",
              "1)loop for-each , 2)loop do-while , 3)ListIterator ");
      
      Pergunta perg10 = new Pergunta("Qual é o indice inicial de uma matriz?",
              "1)Voce pode comecar com qualquer indice. , 2)0 , 3)Isso depende do tipo da matriz. ");
      
      Pergunta perg11 = new Pergunta("Em uma expressao boolian que usa o operador &&,"
              + " o que faria com que essa expressao gerasse um resultado verdadeiro?",
              "1)Se tanto a primeira quanto a segunda condicoes forem falsas ,"
                      + " 2)Se a primeira condicao for falsa, mas a segunda for verdadeira ,"
                      + " 3)Se tanto a primeira quanto a segunda condicoes forem verdadeiras ");
      
      Pergunta perg12 = new Pergunta("Qual dos cenarios a seguir seria ideal para escrever um metodo?",
              "1)Quando voce nao quer encontrar linhas de codigo semelhantes para descrever o comportamento de um objeto."
                      + " , 2)Quando você não quer repetir linhas de código semelhantes para descrever o"
                      + " comportamento de um objeto. ,"
                      + " 3)Para agrupar tipos de dados semelhantes. ");
      
      Pergunta perg13 = new Pergunta("O que é uma matriz?",
              "1)) Uma matriz é um recipiente indexado que contém um conjunto de valores de um único tipo. ,"
                      + " 2)Uma matriz é um recipiente indexado que contém um conjunto de valores de vários tipos. ,"
                      + " 3)Uma matriz é uma maneira de criar várias cópias de um único valor. ");
      
      Pergunta perg14 = new Pergunta("O que eh um objeto?", "1)a representação (instância) de uma classe ,"
              + " 2)uma forma solida , 3)um metodo ");
      
      Pergunta perg15 = new Pergunta("Como deve ser construida a classe main?",
              "1)complexa e o mais longa possivel , 2)curta e objetiva , 3)nao se constroi uma classe main ");

      
       
       //Criar respostas
       Resposta resp1 = new Resposta(3);
       Resposta resp2 = new Resposta(1);
       Resposta resp3 = new Resposta(1);
       Resposta resp4 = new Resposta(2);
       Resposta resp5 = new Resposta(1);
       Resposta resp6 = new Resposta(1);
       Resposta resp7 = new Resposta(1);
       Resposta resp8 = new Resposta(2);
       Resposta resp9 = new Resposta(2);
       Resposta resp10 = new Resposta(1);
       Resposta resp11 = new Resposta(3);
       Resposta resp12 = new Resposta(2);
       Resposta resp13 = new Resposta(1);
       Resposta resp14 = new Resposta(1);
       Resposta resp15 = new Resposta(2);
       
       
       
       System.out.println("Respondam a pergunta escolhendo numeros de 1 a 3: ");
       System.out.println(perg1.getQuery());
       System.out.println(perg1.getAns());
       
       Scanner alt1_1 = new Scanner(System.in);
       int escol1_1 = alt1_1.nextInt();
       Scanner alt2_1 = new Scanner(System.in);
       int escol2_1 = alt2_1.nextInt();
       
      
       if (escol1_1 == 3) {
           System.out.println("Jogador 1, Resposta correta!");
       } else if(escol1_1 != 3 && !perso1Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Jogador1, Resposta correta: " + resp1.getResp());
       }else if(escol1_1 != 3 && !perso2Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta: " + resp1.getResp());
       }else if(escol1_1 != 3 && !perso3Selecionado){
           System.out.println("Jogador1, Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta: " + resp1.getResp());
       }
       
       
        if (escol2_1 == 3) {
           System.out.println("Jogador 2,Resposta correta!");
       } else if(escol2_1 != 3 && !perso1Selecionado){
           System.out.println("Jogador 2, Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta: " + resp1.getResp());
       }else if(escol2_1 != 3 && !perso2Selecionado){
           System.out.println("Jogador 2, Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta: " + resp1.getResp());
       }else if(escol2_1 != 3 && !perso3Selecionado){
           System.out.println("Jogador 2, Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta: " + resp1.getResp());
       }
        System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg2.getQuery());
        System.out.println(perg2.getAns());
        
        Scanner alt1_2 = new Scanner(System.in);
       int escol1_2 = alt1_2.nextInt();
       Scanner alt2_2 = new Scanner(System.in);
       int escol2_2 = alt2_2.nextInt();
       
      
       if (escol1_2 == 1) {
           System.out.println("Jogador 1, Resposta correta!");
       } else if(escol1_2 != 1 && !perso1Selecionado){
           System.out.println("Jogador 1, Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta: " + resp2.getResp());
       }else if(escol1_2 != 1 && !perso2Selecionado){
           System.out.println("Jogador1 ,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta: " + resp2.getResp());
       }else if(escol1_2 != 1 && !perso3Selecionado){
           System.out.println("Jogador 1, Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta: " + resp2.getResp());
       }
       
       
        if (escol2_2 == 1) {
           System.out.println("Jogador 2,Resposta correta!");
       } else if(escol2_2 != 1 && !perso1Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp2.getResp());
       }else if(escol2_2 != 1 && !perso2Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp2.getResp());
       }else if(escol2_2 != 1 && !perso3Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp2.getResp());
       }
       
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg3.getQuery());
        System.out.println(perg3.getAns());
        
        Scanner alt1_3 = new Scanner(System.in);
       int escol1_3 = alt1_3.nextInt();
       Scanner alt2_3 = new Scanner(System.in);
       int escol2_3 = alt2_3.nextInt();
       
      
       if (escol1_3 == 1) {
           System.out.println("Jogador 1,Resposta correta!");
       } else if(escol1_3 != 1 && !perso1Selecionado){
           System.out.println("Jogador 1,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp3.getResp());
       }else if(escol1_3 != 1 && !perso2Selecionado){
           System.out.println("Jogador 1,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp3.getResp());
       }else if(escol1_3 != 1 && !perso3Selecionado){
           System.out.println("Jogador 1,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp3.getResp());
       }
       
       
        if (escol2_3 == 1) {
           System.out.println("Jogador2,Resposta correta!");
       } else if(escol2_3 != 1 && !perso1Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp3.getResp());
       }else if(escol2_3 != 1 && !perso2Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp3.getResp());
       }else if(escol2_3 != 1 && !perso3Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp3.getResp());
       } 
       
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg4.getQuery());
        System.out.println(perg4.getAns());
        
        Scanner alt1_4 = new Scanner(System.in);
       int escol1_4 = alt1_4.nextInt();
       Scanner alt2_4 = new Scanner(System.in);
       int escol2_4 = alt2_4.nextInt();
       
       if (escol1_4 == 2) {
           System.out.println("Jogador1,Resposta correta!");
       } else if(escol1_4 != 2 && !perso1Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp4.getResp());
       }else if(escol1_4 != 2 && !perso2Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp4.getResp());
       }else if(escol1_4 != 2 && !perso3Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp4.getResp());
       }
       
        if (escol2_4 == 2) {
           System.out.println("Jogador2,Resposta correta!");
       } else if(escol2_4 != 2 && !perso1Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp4.getResp());
       }else if(escol2_4 != 2 && !perso2Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp4.getResp());
       }else if(escol2_4 != 2 && !perso3Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp4.getResp());
       } 
       
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg5.getQuery());
        System.out.println(perg5.getAns());
        
        Scanner alt1_5 = new Scanner(System.in);
       int escol1_5 = alt1_5.nextInt();
       Scanner alt2_5 = new Scanner(System.in);
       int escol2_5 = alt2_5.nextInt();
       
       if (escol1_5 == 1) {
           System.out.println("Jogador 1,Resposta correta!");
       } else if(escol1_5 != 1 && !perso1Selecionado){
           System.out.println("Jogador 1,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp5.getResp());
       }else if(escol1_5 != 1 && !perso2Selecionado){
           System.out.println("Jogador 1,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp5.getResp());
       }else if(escol1_5 != 1 && !perso3Selecionado){
           System.out.println("Jogador 1,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp5.getResp());
       }
       
        if (escol2_5 == 1) {
           System.out.println("Jogador2,Resposta correta!");
       } else if(escol2_5 != 1 && !perso1Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp5.getResp());
       }else if(escol2_5 != 1 && !perso2Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp5.getResp());
       }else if(escol2_5 != 1 && !perso3Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp5.getResp());
       }
       
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg6.getQuery());
        System.out.println(perg6.getAns());
        
        Scanner alt1_6 = new Scanner(System.in);
       int escol1_6 = alt1_6.nextInt();
       Scanner alt2_6 = new Scanner(System.in);
       int escol2_6 = alt2_6.nextInt();
       
       if (escol1_6 == 1) {
           System.out.println("Jogador 1, Resposta correta!");
       } else if(escol1_6 != 1 && !perso1Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp6.getResp());
       }else if(escol1_6 != 1 && !perso2Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp6.getResp());
       }else if(escol1_6 != 1 && !perso3Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp6.getResp());
       }
       
        if (escol2_6 == 1) {
           System.out.println("Jogador 2, Resposta correta!");
       } else if(escol2_6 != 1 && !perso1Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp6.getResp());
       }else if(escol2_6 != 1 && !perso2Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp6.getResp());
       }else if(escol2_6 != 1 && !perso3Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp6.getResp());
       } 
        System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg7.getQuery());
        System.out.println(perg7.getAns());
        
       Scanner alt1_7 = new Scanner(System.in);
       int escol1_7 = alt1_7.nextInt();
       Scanner alt2_7 = new Scanner(System.in);
       int escol2_7 = alt2_7.nextInt();
       
       if (escol1_7 == 1) {
           System.out.println("Jogador 1, Resposta correta!");
       } else if(escol1_7 != 1 && !perso1Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp7.getResp());
       }else if(escol1_7 != 1 && !perso2Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp7.getResp());
       }else if(escol1_7 != 1 && !perso3Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp7.getResp());
       }
       
        if (escol2_7 == 1) {
           System.out.println("Jogador 2, Resposta correta!");
       } else if(escol2_7 != 1 && !perso1Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp7.getResp());
       }else if(escol2_7 != 1 && !perso2Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp7.getResp());
       }else if(escol2_7 != 1 && !perso3Selecionado){
           System.out.println("Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp7.getResp());
       }
        
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg8.getQuery());
        System.out.println(perg8.getAns());
        
        Scanner alt1_8 = new Scanner(System.in);
       int escol1_8 = alt1_8.nextInt();
       Scanner alt2_8 = new Scanner(System.in);
       int escol2_8 = alt2_8.nextInt();
       
       if (escol1_8 == 2) {
           System.out.println("Jogador1,Resposta correta!");
       } else if(escol1_8 != 2 && !perso1Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp8.getResp());
       }else if(escol1_8 != 2 && !perso2Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp8.getResp());
       }else if(escol1_8 != 2 && !perso3Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp8.getResp());
       }
       
        if (escol2_8 == 2) {
           System.out.println("Jogador2,Resposta correta!");
       } else if(escol2_8 != 2 && !perso1Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp8.getResp());
       }else if(escol2_8 != 2 && !perso2Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp8.getResp());
       }else if(escol2_8 != 2 && !perso3Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp8.getResp());
       } 
       
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg9.getQuery());
        System.out.println(perg9.getAns());
        
        Scanner alt1_9 = new Scanner(System.in);
       int escol1_9 = alt1_9.nextInt();
       Scanner alt2_9 = new Scanner(System.in);
       int escol2_9 = alt2_9.nextInt();
       
       if (escol1_9 == 2) {
           System.out.println("Jogador1,Resposta correta!");
       } else if(escol1_9 != 2 && !perso1Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp9.getResp());
       }else if(escol1_9 != 2 && !perso2Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp9.getResp());
       }else if(escol1_9 != 2 && !perso3Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp9.getResp());
       }
       
        if (escol2_9 == 2) {
           System.out.println("Jogador2,Resposta correta!");
       } else if(escol2_9 != 2 && !perso1Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           System.out.println("Resposta correta= " + resp9.getResp());
       }else if(escol2_9 != 2 && !perso2Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           System.out.println("Resposta correta= " + resp9.getResp());
       }else if(escol2_9 != 2 && !perso3Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           System.out.println("Resposta correta= " + resp9.getResp());
       } 
       
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg10.getQuery());
        System.out.println(perg10.getAns());
        
        Scanner alt1_10 = new Scanner(System.in);
       int escol1_10 = alt1_10.nextInt();
       Scanner alt2_10 = new Scanner(System.in);
       int escol2_10 = alt2_10.nextInt();
       
      
       if (escol1_10 == 1) {
           System.out.println("Jogador 1, Resposta correta!");
       } else if(escol1_10 != 1 && !perso1Selecionado){
           System.out.println("Jogador 1, Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           
           System.out.println("Resposta correta: " + resp10.getResp());
       }else if(escol1_10 != 1 && !perso2Selecionado){
           System.out.println("Jogador1 ,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp10.getResp());
       }else if(escol1_10 != 1 && !perso3Selecionado){
           System.out.println("Jogador 1, Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp10.getResp());
       }
       
       
        if (escol2_10 == 1) {
           System.out.println("Jogador 2,Resposta correta!");
       } else if(escol2_10 != 1 && !perso1Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp10.getResp());
       }else if(escol2_10 != 1 && !perso2Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp10.getResp());
       }else if(escol2_10 != 1 && !perso3Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println( perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp10.getResp());
       }
        
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg11.getQuery());
        System.out.println(perg11.getAns());
        
        Scanner alt1_11 = new Scanner(System.in);
       int escol1_11 = alt1_11.nextInt();
       Scanner alt2_11 = new Scanner(System.in);
       int escol2_11 = alt2_11.nextInt();
       
      
       if (escol1_11 == 3) {
           System.out.println("Jogador 1, Resposta correta!");
       } else if(escol1_11 != 3 && !perso1Selecionado){
           System.out.println("Jogador 1, Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp11.getResp());
       }else if(escol1_11 != 3 && !perso2Selecionado){
           System.out.println("Jogador1 ,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp11.getResp());
       }else if(escol1_11 != 3 && !perso3Selecionado){
           System.out.println("Jogador 1, Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp11.getResp());
       }
       
       
        if (escol2_11 == 3) {
           System.out.println("Jogador 2,Resposta correta!");
       } else if(escol2_11 != 3 && !perso1Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp11.getResp());
       }else if(escol2_11 != 3 && !perso2Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp11.getResp());
       }else if(escol2_11 != 3 && !perso3Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp11.getResp());
       }
        
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg12.getQuery());
        System.out.println(perg12.getAns());
        
        Scanner alt1_12 = new Scanner(System.in);
       int escol1_12 = alt1_12.nextInt();
       Scanner alt2_12 = new Scanner(System.in);
       int escol2_12 = alt2_12.nextInt();
       
       if (escol1_12 == 2) {
           System.out.println("Jogador1,Resposta correta!");
       } else if(escol1_12 != 2 && !perso1Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp12.getResp());
       }else if(escol1_12 != 2 && !perso2Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp4.getResp());
       }else if(escol1_12 != 2 && !perso3Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp4.getResp());
       }
       
        if (escol2_12 == 2) {
           System.out.println("Jogador2,Resposta correta!");
       } else if(escol2_12 != 2 && !perso1Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp4.getResp());
       }else if(escol2_12 != 2 && !perso2Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp4.getResp());
       }else if(escol2_12 != 2 && !perso3Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp4.getResp());
       }
       
        System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg13.getQuery());
        System.out.println(perg13.getAns());
        
        Scanner alt1_13 = new Scanner(System.in);
       int escol1_13 = alt1_13.nextInt();
       Scanner alt2_13 = new Scanner(System.in);
       int escol2_13 = alt2_13.nextInt();
       
      
       if (escol1_13 == 1) {
           System.out.println("Jogador 1, Resposta correta!");
       } else if(escol1_13 != 1 && !perso1Selecionado){
           System.out.println("Jogador 1, Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp13.getResp());
       }else if(escol1_13 != 1 && !perso2Selecionado){
           System.out.println("Jogador1 ,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp10.getResp());
       }else if(escol1_13 != 1 && !perso3Selecionado){
           System.out.println("Jogador 1, Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp10.getResp());
       }
       
       
        if (escol2_13 == 1) {
           System.out.println("Jogador 2,Resposta correta!");
       } else if(escol2_13 != 1 && !perso1Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp10.getResp());
       }else if(escol2_13 != 1 && !perso2Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp10.getResp());
       }else if(escol2_13 != 1 && !perso3Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp10.getResp());
       } 
        
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg14.getQuery());
        System.out.println(perg14.getAns());
        
        Scanner alt1_14 = new Scanner(System.in);
       int escol1_14 = alt1_14.nextInt();
       Scanner alt2_14 = new Scanner(System.in);
       int escol2_14 = alt2_14.nextInt();
       
      
       if (escol1_14 == 1) {
           System.out.println("Jogador 1, Resposta correta!");
       } else if(escol1_14 != 1 && !perso1Selecionado){
           System.out.println("Jogador 1, Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp14.getResp());
       }else if(escol1_14 != 1 && !perso2Selecionado){
           System.out.println("Jogador1 ,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp10.getResp());
       }else if(escol1_14 != 1 && !perso3Selecionado){
           System.out.println("Jogador 1, Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta: " + resp10.getResp());
       }
             
        if (escol2_14 == 1) {
           System.out.println("Jogador 2,Resposta correta!");
       } else if(escol2_14 != 1 && !perso1Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp10.getResp());
       }else if(escol2_14 != 1 && !perso2Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp10.getResp());
       }else if(escol2_14 != 1 && !perso3Selecionado){
           System.out.println("Jogador 2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp10.getResp());
       }
       
       System.out.println("__________________________________________________________________");
        System.out.println("Proxima pergunta.Respondam a pergunta escolhendo numeros de 1 a 3: ");
        System.out.println(perg15.getQuery());
        System.out.println(perg15.getAns());
        
        Scanner alt1_15 = new Scanner(System.in);
       int escol1_15 = alt1_15.nextInt();
       Scanner alt2_15 = new Scanner(System.in);
       int escol2_15 = alt2_15.nextInt();
       
       if (escol1_15 == 2) {
           System.out.println("Jogador1,Resposta correta!");
       } else if(escol1_15 != 2 && !perso1Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp15.getResp());
       }else if(escol1_15 != 2 && !perso2Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp4.getResp());
       }else if(escol1_15 != 2 && !perso3Selecionado){
           System.out.println("Jogador1,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 2 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp4.getResp());
       }
       
        if (escol2_15 == 2) {
           System.out.println("Jogador2,Resposta correta!");
       } else if(escol2_15 != 2 && !perso1Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Dio perde 10% de vida");
           perso1.setVida((int) (perso1.getVida() -1));
           System.out.println(perso1.getVida());
           if(perso1.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp4.getResp());
       }else if(escol2_15 != 2 && !perso2Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Koichi perde 10% de vida");
           perso2.setVida((int) (perso2.getVida() -1));
           System.out.println(perso2.getVida());
           if(perso2.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp4.getResp());
       }else if(escol2_15 != 2 && !perso3Selecionado){
           System.out.println("Jogador2,Resposta errada");
           System.out.println("Lisa perde 10% de vida");
           perso3.setVida((int) (perso3.getVida() -1));
           System.out.println(perso3.getVida());
           if(perso3.getVida()== 0){
               System.out.println("Jogador 1 venceu, obrigado por jogar");
               return;
           }
           System.out.println("Resposta correta= " + resp4.getResp());
       }
        
        if(!perso1Selecionado && perso1.getVida() > perso2.getVida()) {
            System.out.println("Dio Ganhou!!!");
            System.out.println("Obrigado por jogar!");
        } else if(!perso1Selecionado && perso1.getVida() > perso3.getVida()) {
            System.out.println("Dio Ganhou!!!");
            System.out.println("Obrigado por jogar!");
        } else  if(!perso2Selecionado && perso2.getVida() > perso1.getVida()) {
            System.out.println("Koichi Ganhou!!!");
            System.out.println("Obrigado por jogar!");
        } else if(!perso2Selecionado && perso2.getVida() > perso3.getVida()) {
            System.out.println("Koichi Ganhou!!!");
            System.out.println("Obrigado por jogar!");
        } else if(!perso3Selecionado && perso3.getVida() > perso2.getVida()) {
            System.out.println("Lisa Ganhou!!!");
            System.out.println("Obrigado por jogar!");
        } else if(!perso3Selecionado && perso3.getVida() > perso1.getVida()) {
            System.out.println("Lisa Ganhou!!!");
            System.out.println("Obrigado por jogar!");
        } else{
            System.out.println("Empate");
            System.out.println("Obrigado por jogar!");
        }       
   } 
  }
