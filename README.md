import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class CalculadoraTest {

    @Test
    public void testSoma() {
        Soma soma = new Soma();
        int resultado = soma.somar(2, 3);
        assertEquals(5, resultado);
    }

    @Test
    public void testSubtracao() {
        Subtracao subtracao = new Subtracao();
        int resultado = subtracao.subtrair(5, 3);
        assertEquals(2, resultado);
    }

    @Test
    public void testMultiplicacao() {
        Multiplicacao multiplicacao = new Multiplicacao();
        int resultado = multiplicacao.multiplicar(4, 5);
        assertEquals(20, resultado);
    }

    @Test
    public void testDivisao() {
        Divisao divisao = new Divisao();
        double resultado = divisao.dividir(10, 2);
        assertEquals(5.0, resultado, 0.001);
    }

    public static class Soma {
        public int somar(int a, int b) {
            return a + b;
        }
    }

    public static class Subtracao {
        public int subtrair(int a, int b) {
            return a - b;
        }
    }

    public static class Multiplicacao {
        public int multiplicar(int a, int b) {
            return a * b;
        }
    }

    public static class Divisao {
        public double dividir(double a, double b) {
            if (b == 0) {
                throw new IllegalArgumentException("Divisão por zero não é permitida.");
            }
            return a / b;
        }
    }
}
