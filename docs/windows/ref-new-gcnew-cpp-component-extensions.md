---
title: "REF neue Gcnew (Komponentenerweiterungen für C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
dev_langs:
- C++
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 616117f7274d6f68456aa23614fb354a71982fb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ref-new-gcnew--c-component-extensions"></a>ref new, gcnew (Komponentenerweiterungen für C++)
Die `ref new` -aggregatschlüsselwort ordnet eine Instanz eines Typs, die Garbage Collection auf, wenn das Objekt wird nicht zugegriffen werden kann, die ein Handle zurückgibt ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)) auf das zugeordnete Objekt.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 Bei Arbeitsspeicher für eine Instanz eines durch `ref new` zugeordneten Typs wird die Zuordnung automatisch aufgehoben.  
  
 Ein `ref new`-Vorgang löst `OutOfMemoryException` aus, wenn es nicht verwendet werden kann, um Arbeitsspeicher zuzuordnen.  
  
 Weitere Informationen darüber, wie Arbeitsspeicher für systemeigene C++-Typen zugeordnet und freigegeben wird, finden Sie unter [die neue "und" delete](../cpp/new-and-delete-operators.md).  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 Verwenden Sie `ref new`, um Arbeitsspeicher für Windows-Runtime-Objekte zuzuordnen, deren Lebensdauer zu automatisch verwalten möchten. Die Zuordnung des Objekts wird automatisch aufgehoben, wenn sein Verweiszähler bei 0 liegt. Dies ist der Fall, nachdem die letzte Kopie des Verweises den Gültigkeitsbereich verlassen hat. Weitere Informationen finden Sie unter [Verweisklassen und Strukturen](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 Der Arbeitsspeicher für einen verwalteten Typ (Verweis oder Werttyp) wird durch `gcnew` zugeordnet, und mithilfe der Garbage Collection wird dessen Zuordnung aufgehoben.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel verwendet `gcnew` zum Zuordnen eines „Message“-Objekts verwendet.  
  
```  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 **Beispiel**  
  
 Im folgenden Beispiel wird `gcnew` zum Erstellen eines geschachtelten Werttyps verwendet, der wie ein Verweistyp verwendet werden soll.  
  
```  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
 **Ausgabe**  
  
```Output  
32  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)