---
title: "Vorgehensweise: Deklarieren von Werttypen mit dem Interior_ptr-Schlüsselwort (C + c++ / CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4b42cbbbc175b3d48baa7b7b2e1c1a5b0e4cbf15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-declare-value-types-with-the-interiorptr-keyword-ccli"></a>Gewusst wie: Deklarieren von Werttypen mit dem interior_ptr-Schlüsselwort (C++/CLI)
Ein `interior_ptr` mit einem Werttyp verwendet werden können.  
  
> [!IMPORTANT]
>  Diese Sprachfunktion wird unterstützt, indem Sie die **"/ CLR"** (Compileroption), jedoch nicht von der **/Zw** -Compileroption.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Die folgenden C + c++ / CLI-Beispiel zeigt, wie ein `interior_ptr` mit einem Werttyp.  
  
### <a name="code"></a>Code  
  
```  
// interior_ptr_value_types.cpp  
// compile with: /clr  
value struct V {  
   V(int i) : data(i){}  
   int data;  
};  
  
int main() {  
   V v(1);  
   System::Console::WriteLine(v.data);  
  
   // pointing to a value type  
   interior_ptr<V> pv = &v;  
   pv->data = 2;  
  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
  
   // pointing into a value type  
   interior_ptr<int> pi = &v.data;  
   *pi = 3;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
}  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
1  
2  
2  
3  
3  
3  
```  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 In einen Werttyp der `this` Zeiger Interior_ptr ergibt.  
  
 Im Text einer nicht statischen Memberfunktion eines Werttyps `V`, `this` ist ein Ausdruck vom Typ `interior_ptr<V>` , dessen Wert ist die Adresse des Objekts, für das die Funktion aufgerufen wird.  
  
### <a name="code"></a>Code  
  
```  
// interior_ptr_value_types_this.cpp  
// compile with: /clr /LD  
value struct V {  
   int data;  
   void f() {  
      interior_ptr<V> pv1 = this;  
      // V* pv2 = this;   error  
   }  
};  
```  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgende Beispiel wird gezeigt, wie mit statischen Members der Address-of-Operator verwendet wird.  
  
 Die Adresse eines statischen Members der Visual C++-Typ ergibt einen systemeigenen Zeiger.  Die Adresse eines Typmembers statischen Wert ist ein verwalteter Zeiger, da Typmember Wert auf dem Laufzeitheap belegten wird und von der Garbage Collection verschoben werden kann.  
  
### <a name="code"></a>Code  
  
```  
// interior_ptr_value_static.cpp  
// compile with: /clr  
using namespace System;  
value struct V { int i; };  
  
ref struct G {  
   static V v = {22};   
   static int i = 23;   
   static String^ pS = "hello";   
};  
  
int main() {  
   interior_ptr<int> p1 = &G::v.i;  
   Console::WriteLine(*p1);  
  
   interior_ptr<int> p2 = &G::i;  
   Console::WriteLine(*p2);  
  
   interior_ptr<String^> p3 = &G::pS;  
   Console::WriteLine(*p3);  
}  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
22  
23  
hello  
```  
  
## <a name="see-also"></a>Siehe auch  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)