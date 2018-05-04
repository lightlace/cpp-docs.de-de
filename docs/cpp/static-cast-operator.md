---
title: Static_cast-Operator | Microsoft Docs
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
ms.openlocfilehash: 5a0cd6ea7e2268940febca9e1e564f30d29dcff0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="staticcast-operator"></a>static_cast-Operator
Konvertiert eine *Ausdruck* in den Typ des *Typ-Id,* schon auf Grundlage der Typen, die im Ausdruck vorhanden sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
static_cast <type-id> ( expression )   
```  
  
## <a name="remarks"></a>Hinweise  
 Im Standard-C++ wird zur Laufzeit keine Typüberprüfung durchgeführt, um die Sicherheit der Konvertierung zu gewährleisten. In C++/CX wird eine Überprüfung der Kompilierzeit und der Laufzeit durchgeführt. Weitere Informationen finden Sie unter [Umwandlung](casting.md).  
  
 Der `static_cast`-Operator kann für Vorgänge wie das Konvertieren eines Zeigers auf eine Basisklasse in einen Zeiger auf eine abgeleitete Klasse verwendet werden. Solche Konvertierungen sind nicht immer sicher.  
  
 Im Allgemeinen verwenden Sie `static_cast`, wenn Sie numerische Datentypen wie Enumerationen in ints oder ints in Gleitkommas konvertieren möchten und Sie sicher sind, welche Datentypen in die Konvertierung einbezogen sind. `static_cast`-Konvertierungen sind nicht so sicher wie `dynamic_cast`-Konvertierungen, da `static_cast` zur Laufzeit keine Typüberprüfung durchführt, während `dynamic_cast` dies tut. Eine `dynamic_cast` zu einem mehrdeutigen Zeiger führt zu einem Fehler, wobei eine `static_cast` zurückgegeben wird, als hätte es kein Problem gegeben. Dies kann gefährlich sein. Obwohl `dynamic_cast`-Konvertierungen sicherer sind, funktioniert `dynamic_cast` nur bei Zeigern oder Verweisen, und die Typüberprüfung zur Laufzeit ist ein Mehraufwand. Weitere Informationen finden Sie unter [Dynamic_cast Operator](../cpp/dynamic-cast-operator.md).  
  
 Im folgende Beispiel ist die Zeile `D* pd2 = static_cast<D*>(pb);` nicht sicher, da `D` Felder und Methoden aufweisen kann, die nicht in `B` enthalten sind. Allerdings ist die Zeile `B* pb2 = static_cast<B*>(pd);` eine sichere Konvertierung, da `D` immer alle Elemente von `B` enthält.  
  
```  
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
  
 Im Gegensatz zu [Dynamic_cast](../cpp/dynamic-cast-operator.md), erfolgt keine Überprüfung zur Laufzeit in die `static_cast` Konvertierung `pb`. Das Objekt, auf das mit `pb` gezeigt wird, ist möglicherweise kein Objekt vom Typ `D`. In diesem Fall kann die Verwendung von `*pd2` zu schwerwiegenden Fehlern führen. Beispielsweise kann das Aufrufen einer Funktion, die ein Member der `D`-Klasse, aber nicht der `B`-Klasse ist, eine Zugriffsverletzung verursachen.  
  
 Die Operatoren `dynamic_cast` und `static_cast` verschieben einen Zeiger innerhalb einer Klassenhierarchie. Allerdings beruht `static_cast` ausschließlich auf den Informationen, die in der Umwandlungsanweisung enthalten sind, und kann daher unsicher sein. Zum Beispiel:  
  
```  
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
  
 Wenn `pb` auf ein Objekt vom Typ `B` zeigt und nicht auf die vollständige `D`-Klasse, hat `dynamic_cast` genug Informationen, um null (0) zurückgegeben. Allerdings beruht `static_cast` auf der Assertion des Programmierers, dass `pb` auf ein Objekt vom Typ `D` zeigt und einfach einen Zeiger auf dieses angenommene `D`-Objekt zurückgibt.  
  
 Daher kann `static_cast` die Umkehrung von impliziten Konvertierungen durchführen. In diesem Fall sind die Ergebnisse nicht definiert. Es ist dem Programmierer überlassen zu überprüfen, ob die Ergebnisse einer `static_cast`-Konvertierung sicher sind.  
  
 Dieses Verhalten gilt auch für andere Typen als Klassentypen. Beispielsweise kann `static_cast` für die Konvertierung von int in `char` verwendet werden. Allerdings verfügt das resultierende `char` möglicherweise nicht über genügend Bit, um den gesamten `int`-Wert aufzunehmen. Erneut, es ist dem Programmierer überlassen zu überprüfen, ob die Ergebnisse einer `static_cast` -Konvertierung sicher sind.  
  
 Der `static_cast`-Operator kann auch verwendet werden, um jede implizite Konvertierung auszuführen, einschließlich Standardkonvertierungen und benutzerdefinierter Konvertierungen. Zum Beispiel:  
  
```  
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
  
 Der `static_cast`-Operator kann explizit einen ganzzahligen Wert in einen Enumerationstyp konvertieren. Wenn der Wert des ganzzahligen Typs nicht innerhalb des Bereichs von Enumerationswerten liegt, ist der resultierende Enumerationswert nicht definiert.  
  
 Der `static_cast`-Operator konvertiert einen NULL-Zeigerwert in den NULL-Zeigerwert des Zieltyps.  
  
 Jeder Ausdruck kann durch den `static_cast`-Operator explizit in den Typ "void" konvertiert werden. Der Zieltyp "void" kann optional das Attribut `const`, `volatile` oder `__unaligned` einbeziehen.  
  
 Der `static_cast`-Operator kann kein `const`-, `volatile`- oder `__unaligned`-Attribut umwandeln. Finden Sie unter [Const_cast-Operator](../cpp/const-cast-operator.md) Informationen zum Entfernen dieser Attribute.  
  
 Aufgrund der Gefahr der Ausführung von ungeprüften Umwandlungen in einem verschiebenden Garbage Collector sollte die Verwendung von `static_cast` nur in leistungskritischem Code erfolgen, wenn Sie sicher sind, dass sie ordnungsgemäß funktioniert. Wenn Sie verwenden müssen `static_cast` im Releasemodus, ersetzen Sie diese mit ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md) in Debugbuilds Erfolg.  
  
## <a name="see-also"></a>Siehe auch  
 [Umwandlungsoperatoren](../cpp/casting-operators.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)