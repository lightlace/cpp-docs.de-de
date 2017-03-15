---
title: "Verwenden von Lambdas, Function-Objekten und eingeschr&#228;nkten Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Verwenden von Lambdas, Function-Objekten und eingeschr&#228;nkten Funktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der C\+\+ AMP\-Code, den Sie im Beschleuniger ausführen möchten, ist als Argument in einem Aufruf der [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)\-Methode angegeben.  Als Argument können Sie einen Lambda\-Ausdruck oder ein Funktionsobjekt \(Funktionselement\) verwenden.  Zudem kann mit dem Lambda\-Ausdruck oder dem Funktionsobjekt eine eingeschränkte C\+\+ AMP\-Funktion aufgerufen werden.  In diesem Thema werden Lambdas, Funktionsobjekte und eingeschränkte Funktionen anhand eines Algorithmus zum Hinzufügen von Arrays veranschaulicht.  Im folgenden Beispiel ist der Algorithmus ohne C\+\+ AMP\-Code dargestellt.  Es werden zwei eindimensionale Arrays derselben Länge erstellt.  Die entsprechenden ganzzahligen Elemente werden hinzugefügt und in einem dritten eindimensionalen Array gespeichert.  C\+\+ AMP wird nicht verwendet.  
  
```cpp  
  
void CpuMethod() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        sumCPP[idx] = aCPP[idx] + bCPP[idx];  
    }  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        std::cout << sumCPP[idx] << "\n";  
    }  
}  
  
```  
  
## Lambda\-Ausdruck  
 Das Verwenden eines Lambda\-Ausdrucks ist die einfachste Möglichkeit, den Code mit C\+\+ AMP umzuschreiben.  
  
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
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 Der Lambda\-Ausdruck muss einen Indizierungsparameter und `restrict(amp)` enthalten.  Im Beispiel verfügt das [array\_view](../../parallel/amp/reference/array-view-class.md)`sum` einen Rang von 1.  Daher handelt es sich beim Parameter für die Lambda\-Anweisung um ein [Index](../../parallel/amp/reference/index-class.md)\-Objekt mit dem Rang 1.  Zur Laufzeit wird der Lambda\-Ausdruck einmal für jedes Element im [array\_view](../../parallel/amp/reference/array-view-class.md)\-Objekt ausgeführt.  Weitere Informationen finden Sie unter [Lambda\-Ausdruckssyntax](../../cpp/lambda-expression-syntax.md).  
  
## Function\-Objekt  
 Sie können den Code des Beschleunigers in ein Funktionsobjekt zerlegen.  
  
```cpp  
  
class AdditionFunctionObject  
{  
public:  
    AdditionFunctionObject(const array_view<int, 1>& a,  
        const array_view<int, 1>& b,  
        const array_view<int, 1>& sum  
    )  
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
        AdditionFunctionObject(a, b, sum)  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 Das Funktionsobjekt muss einen Konstruktor und eine Überladung des Funktionsaufrufoperators enthalten.  Im Funktionsaufrufoperator muss ein Indizierungsparameter enthalten sein.  Eine Instanz des Funktionsobjekts wird als zweites Argument der [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)\-Methode übergeben.  In diesem Beispiel werden drei [array\_view](../../parallel/amp/reference/array-view-class.md)\-Objekte an den Konstruktor des Funktionsobjekts übergeben.  Das [array\_view](../../parallel/amp/reference/array-view-class.md)\-Objekt `sum` hat den Rang 1.  Daher handelt es sich beim Parameter des Funktionsaufrufoperators um ein [Index](../../parallel/amp/reference/index-class.md)\-Objekt mit dem Rang 1.  Zur Laufzeit wird die Funktion einmal für jedes Element im [array\_view](../../parallel/amp/reference/array-view-class.md)\-Objekt ausgeführt.  Weitere Informationen finden Sie unter [Funktionsaufruf](../../cpp/function-call-cpp.md) und [Funktionsobjekte in der STL](../../standard-library/function-objects-in-the-stl.md).  
  
## Eingeschränkte C\+\+ AMP\-Funktion  
 Sie können den Code des Beschleunigers weiter zerlegen, indem Sie eine eingeschränkte Funktion erstellen und diese mit einem Lambda\-Ausdruck oder einem Funktionsobjekt aufrufen.  Im folgenden Codebeispiel wird veranschaulicht, wie eine eingeschränkte Funktion mit einem Lambda\-Ausdruck aufgerufen wird.  
  
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
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 Die eingeschränkte Funktion muss `restrict(amp)` enthalten und den in [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md) beschriebenen Einschränkungen entsprechen.  
  
## Siehe auch  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [Lambda\-Ausdruckssyntax](../../cpp/lambda-expression-syntax.md)   
 [Funktionsaufruf](../../cpp/function-call-cpp.md)   
 [Funktionsobjekte in der STL](../../standard-library/function-objects-in-the-stl.md)   
 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)