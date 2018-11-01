---
title: Verwenden von Lambdas, Funktionsobjekten und eingeschränkten Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 854a07055407bc69eb00d4c8e32f96182beea599
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446765"
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>Verwenden von Lambdas, Function-Objekten und eingeschränkten Funktionen

Der C++ AMP-Code, den Sie im Beschleuniger ausführen möchten angegeben ist, als Argument in einem Aufruf der [Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) Methode. Als Argument können Sie einen Lambda-Ausdruck oder ein Funktionsobjekt (Funktionselement) verwenden. Zudem kann mit dem Lambdaausdruck oder dem Funktionsobjekt eine eingeschränkte C++ AMP-Funktion aufgerufen werden. In diesem Thema werden Lambdas, Funktionsobjekte und eingeschränkte Funktionen anhand eines Algorithmus zum Hinzufügen von Arrays veranschaulicht. Im folgenden Beispiel ist der Algorithmus ohne C++ AMP-Code dargestellt. Es werden zwei eindimensionale Arrays derselben Länge erstellt. Die entsprechenden ganzzahligen Elemente werden hinzugefügt und in einem dritten eindimensionalen Array gespeichert. C++ AMP wird nicht verwendet.

```cpp
void CpuMethod() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    for (int idx = 0; idx <5; idx++)
    {
        sumCPP[idx] = aCPP[idx] + bCPP[idx];
    }

    for (int idx = 0; idx <5; idx++)
    {
        std::cout <<sumCPP[idx] <<"\n";
    }
}
```

## <a name="lambda-expression"></a>Lambda-Ausdruck

Das Verwenden eines Lambda-Ausdrucks ist die einfachste Möglichkeit, den Code mit C++ AMP umzuschreiben.

```cpp
void AddArraysWithLambda() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
             sum[idx] = a[idx] + b[idx];
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Der Lambda-Ausdruck muss einen Indizierungsparameter und `restrict(amp)` enthalten. Im Beispiel die [Array_view](../../parallel/amp/reference/array-view-class.md) `sum` Objekt hat den Rang 1. Der Parameter der Lambda-Anweisung aus diesem Grund ist eine [Index](../../parallel/amp/reference/index-class.md) Objekt mit dem Rang 1. Zur Laufzeit wird der Lambda-Ausdruck für jedes Element im einmal ausgeführt der [Array_view](../../parallel/amp/reference/array-view-class.md) Objekt. Weitere Informationen finden Sie unter [Lambda-Ausdruckssyntax](../../cpp/lambda-expression-syntax.md).

## <a name="function-object"></a>Function-Objekt

Sie können den Code des Beschleunigers in ein Funktionsobjekt zerlegen.

```cpp
class AdditionFunctionObject
{
public:
    AdditionFunctionObject(const array_view<int, 1>& a,
    const array_view<int, 1>& b,
    const array_view<int, 1>& sum)
    : a(a), b(b), sum(sum)
    {
    }

    void operator()(index<1> idx) restrict(amp)
    {
        sum[idx] = a[idx] + b[idx];
    }

private:
    array_view<int, 1> a;
    array_view<int, 1> b;
    array_view<int, 1> sum;
};

void AddArraysWithFunctionObject() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        AdditionFunctionObject(a, b, sum));

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Das Funktionsobjekt muss einen Konstruktor und eine Überladung des Funktionsaufrufoperators enthalten. Im Funktionsaufrufoperator muss ein Indizierungsparameter enthalten sein. Eine Instanz des Funktionsobjekts übergeben wird, als das zweite Argument für die [Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) Methode. In diesem Beispiel drei [Array_view](../../parallel/amp/reference/array-view-class.md) Objekte an den Konstruktor des Funktionsobjekts übergeben werden. Die [Array_view](../../parallel/amp/reference/array-view-class.md) Objekt `sum` hat den Rang 1. Der Parameter des Funktionsaufrufoperators aus diesem Grund ist eine [Index](../../parallel/amp/reference/index-class.md) Objekt mit dem Rang 1. Zur Laufzeit die Funktion einmal ausgeführt für jedes Element in der [Array_view](../../parallel/amp/reference/array-view-class.md) Objekt. Weitere Informationen finden Sie unter [Funktionsaufruf](../../cpp/function-call-cpp.md) und [Funktionsobjekte in der C++-Standardbibliothek](../../standard-library/function-objects-in-the-stl.md).

## <a name="c-amp-restricted-function"></a>Eingeschränkte C++ AMP-Funktion

Sie können den Code des Beschleunigers weiter zerlegen, indem Sie eine eingeschränkte Funktion erstellen und diese mit einem Lambdaausdruck oder einem Funktionsobjekt aufrufen. Im folgenden Codebeispiel wird veranschaulicht, wie eine eingeschränkte Funktion mit einem Lambdaausdruck aufgerufen wird.

```cpp
void AddElementsWithRestrictedFunction(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)
{
    sum[idx] = a[idx] + b[idx];
}

void AddArraysWithFunction() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<int, 1> a(5, aCPP);

    array_view<int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
            AddElementsWithRestrictedFunction(idx, sum, a, b);
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Die eingeschränkte Funktion muss enthalten `restrict(amp)` und die in beschriebenen Einschränkungen entsprechen [einschränken (C++-AMP)](../../cpp/restrict-cpp-amp.md).

## <a name="see-also"></a>Siehe auch

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Lambdaausdruckssyntax](../../cpp/lambda-expression-syntax.md)<br/>
[Funktionsaufruf](../../cpp/function-call-cpp.md)<br/>
[Funktionsobjekte in der C++-Standardbibliothek](../../standard-library/function-objects-in-the-stl.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)