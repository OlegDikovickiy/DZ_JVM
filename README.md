# DZ_JVM

public class JvmComprehension {

    public static void main(String[] args) {
        int i = 1;                      // 1. Медотод main() создает новый фрейм с памятью в стеке
        Object o = new Object();        // 2. Создаем новый объект, для которого выделяется память в хипе и добавляется ссылка в переменную "o", 
                                        //    отправляет ее в тот же фрейм в стеке
        Integer ii = 2;                 // 3. Выделяем память в хипе и добавляем ссылку в стек
        printAll(o, i, ii);             // 4. Вызовом метода printAll в стеке запускается новый фрейм 
        System.out.println("finished"); // 7. Создается новый фрейм в стеке для метода println
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5. Выделяем память в хипе и добавляем ссылку в стек
        System.out.println(o.toString() + i + ii);  // 6. Создается новый фрейм в стеке для метода println, при инициализации объектов будет вызван метод toString,
                                                    //     который создаст еще один фрейм в стеке
    }
}
