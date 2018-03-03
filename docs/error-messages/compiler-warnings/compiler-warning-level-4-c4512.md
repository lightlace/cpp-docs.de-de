---
title: Compilerwarnung (Stufe 4) C4512 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4512
dev_langs:
- C++
helpviewer_keywords:
- C4512
ms.assetid: afb68995-684a-4be5-a73a-38d7a16dc030
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd2e50f97cfc0242e1ac4af93f2d6609ff4b59cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4512"></a>Compilerwarnung (Stufe 4) C4512
'Klasse': Zuweisungsoperator konnte nicht generiert werden  
  
 Der Compiler kann keinen Zuweisungsoperator für die angegebene Klasse generieren. Es wurde kein Zuweisungsoperator erstellt.  
  
 Ein Zuweisungsoperator für die Basisklasse, auf die nicht von der abgeleiteten Klasse zugegriffen werden kann, kann diese Warnung verursachen.  
  
 Um diese Warnung zu vermeiden, geben Sie einen benutzerdefinierten Zuweisungsoperator für die Klasse an.  
  
 Der Compiler generiert auch eine Zuweisungs-Operator-Funktion für eine Klasse, die keine definiert. Dieser Zuweisungsoperator fungiert als memberspezifische Kopie der Datenmember eines Objekts. Da `const`-Datenelemente nicht nach der Initialisierung geändert werden können, wenn die Klasse ein `const`-Element enthält, würde der standardmäßige Zuweisungsoperator nicht funktionieren. Ein weiterer Grund für die C4512-Warnung ist eine Deklaration eines nicht statischen Datenmembers des Verweistyps. Ziel ist es, einen nicht kopierbaren Typ zu erstellen, Sie müssen auch die Erstellung eines Standardkopiekonstruktors verhindern.  
  
 Sie können die Warnung C4512 für Ihren Code auf eine von drei Arten beheben:  
  
-   Definieren Sie explizit einen Zuweisungsoperator für die Klasse.  
  
-   Entfernen Sie **const** oder den Zuweisungsoperator aus dem Datenelement in der Klasse.  
  
-   Verwenden Sie die #pragma [Warnung](../../preprocessor/warning.md) Anweisung zur Unterdrückung der Warnung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4512 generiert.  
  
```  
// C4512.cpp  
// compile with: /EHsc /W4  
// processor: x86  
  
class Base {  
private:  
   const int a;  
  
public:  
   Base(int val = 0) : a(val) {}  
   int get_a() { return a; }  
};   // C4512 warning  
  
class Base2 {  
private:  
   const int a;  
  
public:  
   Base2(int val = 0) : a(val) {}  
   Base2 & operator=( const Base2 & ) { return *this; }  
   int get_a() { return a; }  
};  
  
// Type designer intends this to be non-copyable because it has a   
// reference member  
class Base3  
{  
private:  
   char& cr;  
  
public:  
   Base3(char& r) : cr(r) {}  
   // Uncomment the following line to explicitly disable copying:  
   // Base3(const Base3&) = delete;   
};   // C4512 warning  
  
int main() {  
   Base first;  
   Base second;  
  
   // OK  
   Base2 first2;  
   Base2 second2;  
  
   char c = 'x';  
   Base3 first3(c);  
   Base3 second3 = first3; // C2280 if no default copy ctor  
}  
```