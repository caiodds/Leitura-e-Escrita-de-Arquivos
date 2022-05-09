# Leitura-e-Escrita-de-Arquivos

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;
public class leitura {
    public static void main(String[] args) throws IOException {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Deseja ler qual arquivo?");
        System.out.println("(1) Tarefas");
        System.out.println("(2) Registros");
        System.out.println("(3) Criar");
        String leitura = scanner.next();

            switch (leitura){
                case "Tarefas":
                    Path arquivos = Paths.get("C:\\Users\\Nicoly Alves\\Desktop\\tarefas.txt");
                    List<String> linhass = Files.readAllLines(arquivos);

                    for (int i = 0; i < linhass.size();i++ ) {
                        String nome = linhass.get(i);
                        System.out.println("Tarefas "+nome);
                    }
                    break;
                case "Registros":
                    Path arquivoss = Paths.get("C:\\Users\\Nicoly Alves\\Desktop\\Registro.txt");
                    List<String> linha = Files.readAllLines(arquivoss);

                    for (int i = 0; i < linha.size();i++ ) {
                        String nome = linha.get(i);
                        System.out.println("Registrados "+nome);
                    }
                    break;
                case "Criar":
                    ArrayList<String> linhas = new ArrayList<>();

                    for (int i = 0; i < 5; i++){
                        System.out.print("Registro " + i + ": ");
                        String nome = scanner.nextLine();

                        linhas.add(nome);
                    }

                    Path arquivo = Paths.get("C:\\Users\\Nicoly Alves\\Desktop\\Arquivos.txt");
                    Files.write(arquivo, linhas);

                    scanner.close();
                    System.out.println("Fim...");
            }
    }
            }
