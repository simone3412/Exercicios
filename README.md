# Exercicios
Exercicios_Classes
using System;
using System.Collections.Generic;
using System.Text;

namespace Classe_01
{
    class Conta_Corrente
    {
        // atriubutos
        public string titular;
        public float[] saldo = new float[3];

        public Conta_Corrente()
        {

        }

        // metodos

        public float CalcSoma()
        {

            byte i = 0;
            float soma;
            soma = 0;

            for (i = 0; i <= 2; i++)
            {
                soma = soma + saldo[i];
            }
            return soma;
        }

        public float CMedia(float totalDigitado)
        {

            return totalDigitado / 3;


        }










    }

}
using System;
using System.Collections.Generic;
using System.Text;

namespace Classe_01
{
    class CPoupanca : Conta_Corrente
    {
        CPoupanca() : base()
        {

        }

        // atributos
        public int NumeroConta = 0;


        // metodo







    }
}
using System;

namespace Classe_01
{
    class Program
    {
        static void Main(string[] args)
        {
            // instanciando

            float valorSomado = 0;

            Conta_Corrente CONTA = new Conta_Corrente();
            CPoupanca dados  = new CPoupanca ();
            Console.WriteLine("Digite o nome do titular:  ");

            CONTA.titular = Console.ReadLine();

            Console.WriteLine("Digite os últimos 3 valores depositados na conta corrente:  ");
         

            for (int i =0; i<=2; i++)
            {
                Console.WriteLine("Saldo.......: ", i + 1);
                CONTA.saldo[i] = float.Parse(Console.ReadLine());

            }

            Console.WriteLine("____");

            Console.WriteLine("Digite os últimos 3 valores depositados na conta poupança:  ");

            for (int i = 0; i <= 2; i++)
            {
                Console.WriteLine("Saldo.......: ", i + 1);
                dados.saldo[i] = float.Parse(Console.ReadLine());

            }

            Console.WriteLine("____");
            valorSomado = CONTA.CalcSoma();
            Console.WriteLine("Apresentando resultados da conta corrente");
            Console.WriteLine("Valor total somado: "+ valorSomado);
            Console.WriteLine("Nome titular: " + CONTA.titular);
            Console.WriteLine("Saldo Conta:    " + CONTA.CalcSoma());
            Console.WriteLine("Média Saldo da Conta:    " + CONTA.CMedia(valorSomado));
            Console.WriteLine("____");
            valorSomado = dados.CalcSoma();
            Console.WriteLine("Apresentando resultados da conta poupança");
            Console.WriteLine("Valor Total somado: " + valorSomado);
            Console.WriteLine("Média Saldo da Poupança:    " + dados.CMedia(valorSomado));
            Console.ReadKey();





        }
    }
}
