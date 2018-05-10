---
title: Übersicht über Generika in Visual C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generics [C++], about generics
- default initializers [C++]
- type parameters [C++]
- constructed types
- type arguments [C++]
- constructed types, open [C++]
- open constructed types [C++]
- constructed types, closed [C++]
ms.assetid: 21f10637-0fce-4916-b925-6c86a126d3aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19200e3c3c4ed67960905b697187dbb6b37a65e9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="overview-of-generics-in-visual-c"></a>Übersicht über Generika in Visual C++
Generika sind parametrisierte Typen, die von der common Language Runtime unterstützt. Ein parametrisierter Typ ist ein Typ, der mit einem unbekannten Typparameter definiert ist, die angegeben wird, wenn die generische verwendet wird.  
  
## <a name="why-generics"></a>Warum Generika?  
 C++ unterstützt, und beide Vorlagen und Generika unterstützen parametrisierte Typen um typisierte Auflistungsklassen zu erstellen. Allerdings bieten Vorlagen, Zeitpunkt der Kompilierung Parametrisierung. Sie können nicht auf eine Assembly verweisen, die eine Vorlagendefinition enthält, und erstellen neue spezialisierungen der Vorlage. Nach dem Kompilieren, sucht eine spezialisierte Vorlage wie jede andere Klasse oder Methode. Im Gegensatz dazu werden Generika in MSIL als ein parametrisierter Typ, die bekanntermaßen von der Laufzeit ein parametrisierter Typ ausgegeben; Quellcode, die eine Assembly mit einem generischen Typ verweist, kann spezialisierungen des generischen Typs erstellen. Weitere Informationen zu den Vergleich von Visual C++-Vorlagen und Generika, finden Sie unter [Generika und Vorlagen (Visual C++)](../windows/generics-and-templates-visual-cpp.md).  
  
## <a name="generic-functions-and-types"></a>Generische Funktionen und Typen  
 Klassentypen, solange sie verwaltete Datentypen sind möglicherweise generisch sein. Ein Beispiel hierfür ist möglicherweise eine `List` Klasse. Der Typ eines Objekts in der Liste wäre der Typparameter. Wenn Sie die erforderliche eine `List` Klasse für viele verschiedene Arten von Objekten, bevor Generika, Sie verwendet haben können, eine `List` , akzeptiert **System:: Object** als Elementtyp. Aber jedes Objekt (einschließlich Objekte des falschen Typs) würde in der Liste verwendet werden können. Eine solche Liste würde eine nicht typisierte Auflistungsklasse aufgerufen werden. Sie könnten bestenfalls Typ, der zur Laufzeit überprüft und eine Ausnahme auslösen. Oder Sie haben eine Vorlage, die die generische Quality nach der Kompilierung in eine Assembly verloren gehen würde verwendet. Consumern der Assembly konnte eigene spezialisierungen der Vorlage nicht erstellt werden. Generika können Sie typisierte Auflistungsklassen, z. B. erstellen `List<int>` (als "Von" Int "Liste" gelesen) und `List<double>` ("Liste der Double") dem einen Fehler während der Kompilierung generieren würden, würden Sie versuchen, einen Typ zu konzentrieren, die der Sammlung war nicht darauf ausgelegt, in der typisierten akzeptieren Auflistung. Darüber hinaus bleiben diese Typen generische, nachdem sie kompiliert werden.  
  
 Eine Beschreibung der Syntax von generischen Klassen finden Sie ggf. unter [generische Klassen (C + c++ / CLI)](../windows/generic-classes-cpp-cli.md) `.` einen neuen Namespace <xref:System.Collections.Generic>, führt einen Satz von parametrisierten Auflistungstypen, einschließlich <xref:System.Collections.Generic.Dictionary%602>, <xref:System.Collections.Generic.List%601>und <xref:System.Collections.Generic.LinkedList%601>.  
  
 Sowohl Instanz und Memberfunktionen von statischen Klassen, Delegaten und globale Funktionen möglicherweise auch generisch sein. Generische Funktionen können erforderlich sein, wenn die Funktion Parameter eines unbekannten Typs sind oder wenn die Funktion selbst mit generischen Typen arbeiten muss. In vielen Fällen, in denen **System:: Object** verwendet wurde in der Vergangenheit als Parameter für einen unbekannten Typ ein generischer Typparameter kann stattdessen verwendet werden, damit mehr als typsicherer Code. Jeder Versuch, einen Typ übergeben, der die Funktion für nicht entworfen wurde, würde zum Zeitpunkt der Kompilierung als Fehler gekennzeichnet werden. Mit **System:: Object** als Funktionsparameter, das unbeabsichtigten übergeben eines Objekts, dass die Funktion vorgesehen wurde nicht für den Umgang mit würde nicht erkannt, und müssten Sie umgewandelt unbekannten Objekttyps, der einen bestimmten Typ in der Funktionsrumpf, und das Konto für die Möglichkeit, dass eine InvalidCastException-Ausnahme. Mit einer generischen würde Code versucht, ein Objekt an die Funktion übergeben einen Typenkonflikt, damit der Hauptteil der Funktion gewährleistet ist, haben Sie den richtigen Typ.  
  
 Die gleichen Vorteile gelten für Auflistungsklassen zu Generika erstellt. Auflistungsklassen, die in der Vergangenheit verwenden **System:: Object** zum Speichern von Elementen in einer Auflistung. Einfügen von Objekten eines Typs, der die Auflistung für nicht entworfen wurde wurde zum Zeitpunkt der Kompilierung und häufig auch nicht, wenn die Objekte eingefügt wurden, nicht gekennzeichnet. Normalerweise würde ein Objekt zu einem anderen Typ umgewandelt werden, wenn es in der Auflistung zugegriffen wurde. Nur, wenn die Umwandlung Fehler wäre die unerwartete Typ erkannt. Generika löst dieses Problem zur Kompilierzeit, durch das Erkennen von jeglicher Code, der einen Typ, die nicht übereinstimmen eingefügt (oder implizit zu konvertieren) der Typparameter der generischen Auflistung.  
  
 Eine Beschreibung der Syntax, finden Sie unter [generische Funktionen (C + c++ / CLI)](../windows/generic-functions-cpp-cli.md).  
  
## <a name="terminology-used-with-generics"></a>Mit Generika-Terminologie  
  
##### <a name="type-parameters"></a>Typparameter  
 Eine generische Deklaration enthält eine oder mehrere unbekannte Typen, die als bekannt *Typparameter*. Typparameter werden ein Name zugewiesen, das für den Typ innerhalb des Texts der generischen Deklaration steht. Der Typparameter wird als ein Typ innerhalb des Texts der generischen Deklaration verwendet. Liste der generischen Deklaration < T\> enthält den Typparameter T.  
  
##### <a name="type-arguments"></a>Typargumente  
 Die *Typargument* ist der tatsächliche Typ anstelle der Typparameter verwendet werden, wenn die generische für einen bestimmten Typ oder Typen spezialisiert ist. Beispielsweise `int` entspricht dem Typargument in `List<int>`. Werttypen und Handletypen sind die einzigen Typen, die als generisches Typargument zulässig.  
  
##### <a name="constructed-type"></a>Konstruierten Typ  
 Aus einem generischen Typ erstellter Typ wird als bezeichnet eine *konstruierter Typ*. Ein Typ, der nicht vollständig angegeben, wie z. B. `List<T>` ist ein *öffnen konstruierten Typ*; einen Typ vollständig angegeben, wie z. B. `List<double>,` ist ein *geschlossen konstruierten Typ* oder *spezialisierten Typ* . Offene konstruierte Typen dürfen in der Definition der andere generische Typen oder Methoden verwendet werden und können nicht vollständig angegeben werden, bis der einschließenden generischen selbst angegeben ist. Folgendes ist z. B. eine Verwendung einen offenen konstruierten Typ als Basisklasse für eine generische:  
  
 `// generics_overview.cpp`  
  
 `// compile with: /clr /c`  
  
 `generic <typename T>`  
  
 `ref class List {};`  
  
 `generic <typename T>`  
  
 `ref class Queue : public List<T> {};`  
  
##### <a name="constraint"></a>Constraint  
 Eine Einschränkung ist eine Einschränkung für die Typen, die wie ein Typparameter verwendet werden kann. Eine angegebene generische Klasse könnte z. B. akzeptieren nur Klassen, die von einer bestimmten Klasse erben oder eine angegebene Schnittstelle implementieren. Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C + c++ / CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="reference-types-and-value-types"></a>Referenztypen und Werttypen  
 Handles und Werttypen können als Typargumente verwendet werden. In der generischen Methodendefinition, in dem beide Typen verwendet werden kann, ist die Syntax, die von Verweistypen. Z. B. die **->** Operator wird verwendet, um die Member des Typs des Typparameters zugreifen, und zwar unabhängig davon, ob der Typ, der schließlich verwendet ein Verweistyp oder ein Werttyp ist. Wenn ein Werttyp als Typargument verwendet wird, generiert die Laufzeit Code, der die Werttypen, die direkt ohne boxing von Werttypen verwendet.  
  
 Wenn einen Verweistyp als generisches Typargument verwendet wird, verwenden Sie die Handle-Syntax. Wenn einen Werttyp als generisches Typargument verwendet wird, verwenden Sie den Namen des Typs direkt.  
  
 `// generics_overview_2.cpp`  
  
 `// compile with: /clr`  
  
 `generic <typename T>`  
  
 `ref class GenericType {};`  
  
 `ref class ReferenceType {};`  
  
 `value struct ValueType {};`  
  
 `int main() {`  
  
 `GenericType<ReferenceType^> x;`  
  
 `GenericType<ValueType> y;`  
  
 `}`  
  
## <a name="type-parameters"></a>Typparameter  
 Der Typparameter in einer generischen Klasse werden wie andere Bezeichner behandelt. Da der Typ nicht bekannt ist, bestehen jedoch Einschränkungen zur jeweiligen Verwendung. Member und Methoden der Klasse von Type-Parameter beispielsweise kann nicht verwenden, es sei denn, der der Typparameter bekannt ist, dass diese Member unterstützen. Zugriff auf einen Member über den Typparameter angeben, müssen Sie den Typ mit dem Element um Einschränkungsliste des Typparameters, also hinzufügen.  
  
 `// generics_overview_3.cpp`  
  
 `// compile with: /clr`  
  
```  
interface class I {  
   void f1();  
   void f2();  
};  
  
ref struct R : public I {  
   virtual void f1() {}  
   virtual void f2() {}   
   virtual void f3() {}   
};  
  
generic <typename T>  
where T : I  
void f(T t) {  
   t->f1();  
   t->f2();  
   safe_cast<R^>(t)->f3();  
}  
  
int main() {  
   f(gcnew R());  
}  
```  
  
 Diese Einschränkungen gelten auch Operatoren. Ein nicht eingeschränkte generischen Typparameter können nicht die `==` und `!=` Operatoren zum Vergleichen von zwei Instanzen des Typparameters, für den Fall, dass der Typ dieser Operatoren nicht unterstützt. Diese Überprüfungen werden für Generika erforderlich, aber nicht für Vorlagen, da Generika zur Laufzeit mit einer Klasse spezialisiert werden können, erfüllt die Einschränkungen aus, wird er zu spät für die Verwendung von ungültigen Elementen zu überprüfen.  
  
 Eine Standardinstanz des Typparameters kann erstellt werden, mithilfe der `()` Operator. Zum Beispiel:  
  
 `T t = T();`  
  
 wobei `T` ein Typparameter einer generischen Klasse oder Methodendefinition ist, wird die Variable auf den Standardwert initialisiert. Wenn `T` ist eine Verweisklasse, es wird ein null-Zeiger; sein, wenn `T` eine Wertklasse ist das Objekt wird mit 0 (null) initialisiert. Hierbei spricht einen *Standard Initialisierer*.  
  
## <a name="see-also"></a>Siehe auch  
 [Generika](../windows/generics-cpp-component-extensions.md)