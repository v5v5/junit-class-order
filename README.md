
# Создать класс

package ru.itasystems.monsys.tests.rus_sports_fee;

import org.junit.jupiter.api.ClassDescriptor;
import org.junit.jupiter.api.ClassOrderer;
import org.junit.jupiter.api.ClassOrdererContext;

public class ClassOrder implements ClassOrderer {
    @Override
    public void orderClasses(ClassOrdererContext classOrdererContext) {
        classOrdererContext.getClassDescriptors().sort(
                (ClassDescriptor d1, ClassDescriptor d2) -> {
                    String className1 = d1.getTestClass().getName();
                    String className2 = d2.getTestClass().getName();

                    if (className1.contains("test_package_48374")) {
                        return -1;
                    }
                    if (className2.contains("test_package_48374")) {
                        return 1;
                    }
                    if (className1.contains("test_package_34534534")) {
                        return -1;
                    }
                    if (className2.contains("test_package_34534534")) {
                        return 1;
                    }
                    if (className1.contains("test_package_756757")) {
                        return -1;
                    }
                    if (className2.contains("test_package_756757")) {
                        return 1;
                    }
                    if (className1.contains("test_package_86786")) {
                        return -1;
                    }
                    if (className2.contains("test_package_86786")) {
                        return 1;
                    }
                    return 0;
                }
        );
    }
}

# в файле junit-platform.properties указать
junit.jupiter.testclass.order.default=ru.itasystems.monsys.tests.rus_sports_fee.ClassOrder


