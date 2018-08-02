---
title: Static_cast-Operator | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- static_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b01e9799a1f8b03406750dca0b486c6c4d0f655
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466695"
---
# <a name="staticcast-operator"></a>static_cast-Operator
Konvertiert eine *Ausdruck* in den Typ des *Typ-Id,* nur auf Grundlage der Typen, die in diesem Ausdruck vorhanden sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
static_cast <type-id> ( expression )   
```  
  
## <a name="remarks"></a>Hinweise  
 Im Standard-C++ wird zur Laufzeit keine Typüberprüfung durchgeführt, um die Sicherheit der Konvertierung zu gewährleisten. In C++/CX wird eine Überprüfung der Kompilierzeit und der Laufzeit durchgeführt. Weitere Informationen finden Sie unter [Umwandlung](casting.md).  
  
 Die **"static_cast"** -Operator kann für Vorgänge wie das Konvertieren eines Zeigers auf eine Basisklasse in einen Zeiger auf eine abgeleitete Klasse verwendet werden. Solche Konvertierungen sind nicht immer sicher.  
  
 Im Allgemeinen verwenden Sie **"static_cast"** numerische Datentypen wie Enumerationen in Ints oder Ints in Gleitkommas, und Sie konvertieren möchten, sind bestimmte Datentypen bei der Konvertierung beteiligt. **"static_cast"** Konvertierungen sind nicht so sicher wie **Dynamic_cast** Konvertierungen, da **"static_cast"** überprüft keine Laufzeit-Typinformationen auf, während er sich **Dynamic_cast** führt. Ein **Dynamic_cast** zu einem mehrdeutigen Zeiger schlägt fehl, während eine **"static_cast"** zurückgibt, als hätte es kein Problem; Dies kann gefährlich sein. Obwohl **Dynamic_cast** -Konvertierungen sicherer sind, **Dynamic_cast** nur funktioniert auf Zeiger oder Verweise, und die typüberprüfung zur Laufzeit ein Mehraufwand ist. Weitere Informationen finden Sie unter [Dynamic_cast-Operator](../cpp/dynamic-cast-operator.md).  
  
 Im folgende Beispiel ist die Zeile `D* pd2 = static_cast<D*>(pb);` nicht sicher, da `D` Felder und Methoden aufweisen kann, die nicht in `B` enthalten sind. Allerdings ist die Zeile `B* pb2 = static_cast<B*>(pd);` eine sichere Konvertierung, da `D` immer alle Elemente von `B` enthält.  
  
```cpp 
// static_cast_Operator.cpp  
// compile with: /LD  
class B {};  
  
class D : public B {};  
  
void f(B* pb, D* pd) {  
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields  
                                   // and methods that are not in B.  
  
   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always  
                                   // contains all of B.  
}  
```  
  
 Im Gegensatz zu [Dynamic_cast](../cpp/dynamic-cast-operator.md), keine Laufzeit wird überprüft, auf die **"static_cast"** Konvertierung `pb`. Das Objekt, auf das mit `pb` gezeigt wird, ist möglicherweise kein Objekt vom Typ `D`. In diesem Fall kann die Verwendung von `*pd2` zu schwerwiegenden Fehlern führen. Beispielsweise kann das Aufrufen einer Funktion, die ein Member der `D`-Klasse, aber nicht der `B`-Klasse ist, eine Zugriffsverletzung verursachen.  
  
 Die **Dynamic_cast** und **"static_cast"** Operatoren verschieben einen Zeiger innerhalb einer Klassenhierarchie. Allerdings **"static_cast"** basiert ausschließlich auf die Informationen in der Cast-Anweisung angegeben und kann daher unsicher sein. Zum Beispiel:  
  
```cpp 
// static_cast_Operator_2.cpp  
// compile with: /LD /GR  
class B {  
public:  
   virtual void Test(){}  
};  
class D : public B {};  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  
   D* pd2 = static_cast<D*>(pb);  
}  
```  
  
 Wenn `pb` tatsächlich auf ein Objekt vom Typ `D` zeigt, erhalten `pd1` und `pd2` den gleichen Wert. Sie rufen außerdem den gleichen Wert ab, wenn `pb == 0`.  
  
 Wenn `pb` verweist auf ein Objekt des Typs `B` und nicht auf die vollständige `D` Klasse, dann **Dynamic_cast** genug Informationen, um NULL zurückzugeben. Allerdings **"static_cast"** basiert auf der Assertion des Programmierers, `pb` verweist auf ein Objekt des Typs `D` und gibt einfach einen Zeiger auf dieses angenommene `D` Objekt.  
  
 Folglich **"static_cast"** möglich, dass die Umkehrung von impliziten Konvertierungen, die in diesem Fall sind die Ergebnisse nicht definiert. Es ist dem Programmierer überlassen zu überprüfen, ob die Ergebnisse einer **"static_cast"** -Konvertierung sicher sind.  
  
 Dieses Verhalten gilt auch für andere Typen als Klassentypen. Z. B. **"static_cast"** können verwendet werden, um eine ganze Zahl zum Konvertieren einer **Char**. Allerdings die resultierende **Char** verfügen möglicherweise nicht über genügend Bits zum Speichern des gesamtes **Int** Wert. In diesem Fall es ist dem Programmierer überlassen zu überprüfen, ob die Ergebnisse einer **"static_cast"** -Konvertierung sicher sind.  
  
 Die **"static_cast"** Operator kann auch verwendet werden, um jede implizite Konvertierung, einschließlich standardkonvertierungen und benutzerdefinierte Konvertierungen durchführen. Zum Beispiel:  
  
```cpp 
// static_cast_Operator_3.cpp  
// compile with: /LD /GR  
typedef unsigned char BYTE;  
  
void f() {  
   char ch;  
   int i = 65;  
   float f = 2.5;  
   double dbl;  
  
   ch = static_cast<char>(i);   // int to char  
   dbl = static_cast<double>(f);   // float to double  
   i = static_cast<BYTE>(ch);  
}  
```  
  
 Die **"static_cast"** Operator kann explizit einen ganzzahligen Wert in einen Enumerationstyp konvertieren. Wenn der Wert des ganzzahligen Typs nicht innerhalb des Bereichs von Enumerationswerten liegt, ist der resultierende Enumerationswert nicht definiert.  
  
 Die **"static_cast"** -Operator konvertiert einen null-Zeiger-Wert, der null-Zeigerwert des Zieltyps.  
  
 Jeder Ausdruck explizit in den Typ von "void" konvertiert werden kann die **"static_cast"** Operator. Der Zieltyp "void" kann optional enthalten die **const**, **flüchtige**, oder **__unaligned** Attribut.  
  
 Die **"static_cast"** Operator nicht umwandeln der **const**, **flüchtige**, oder **__unaligned** Attribute. Finden Sie unter [Const_cast-Operator](../cpp/const-cast-operator.md) Informationen zum Entfernen dieser Attribute.  
  
 Aufgrund der Gefahr der Ausführung von ungeprüften Umwandlungen auf einem leistungskritischem Garbage Collector, die Verwendung von **"static_cast"** sollte nur in leistungskritischen Code sein, wenn Sie sicher, dass sie ordnungsgemäß funktioniert sind. Wenn Sie verwenden müssen **"static_cast"** im Releasemodus, ersetzen Sie sie durch ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md) in den Debugbuilds, um Erfolg zu gewährleisten.  
  
## <a name="see-also"></a>Siehe auch  
 [Umwandlungsoperatoren](../cpp/casting-operators.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)