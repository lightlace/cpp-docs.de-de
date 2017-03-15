---
title: "ref new, gcnew  (C++ Component Extensions)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "gcnew"
  - "ref new"
  - "gcnew_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ref new keyword (C++)"
  - "gcnew keyword [C++]"
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
caps.latest.revision: 24
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# ref new, gcnew  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das `ref new`\-Aggregatschlüsselwort ordnet eine Instanz eines Typs zu, der per Garbage Collection gesammelt wird, wenn auf das Objekt nicht mehr zugegriffen werden kann, wodurch ein Handle \([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)\) zum zugeordneten Objekt zurückgegeben wird.  
  
## Alle Laufzeiten  
 Bei Arbeitsspeicher für eine Instanz eines durch `ref new` zugeordneten Typs wird die Zuordnung automatisch aufgehoben.  
  
 Ein `ref new`\-Vorgang löst `OutOfMemoryException` aus, wenn es nicht verwendet werden kann, um Arbeitsspeicher zuzuordnen.  
  
 Weitere Informationen über die Zuordnung und Aufhebung der Zuordnung von Arbeitsspeicher für systemeigene C\+\+\-Typen finden Sie unter [Die Operatoren new und delete](../cpp/new-and-delete-operators.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Verwenden Sie `ref new`, um Arbeitsspeicher für Windows\-Runtime\-Objekte zuzuordnen, deren Lebensdauer zu automatisch verwalten möchten.  Die Zuordnung des Objekts wird automatisch aufgehoben, wenn sein Verweiszähler bei 0 liegt. Dies ist der Fall, nachdem die letzte Kopie des Verweises den Gültigkeitsbereich verlassen hat.  Weitere Informationen finden Sie unter [Verweisklassen und Strukturen \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 Der Arbeitsspeicher für einen verwalteten Typ \(Verweis oder Werttyp\) wird durch `gcnew` zugeordnet, und mithilfe der Garbage Collection wird dessen Zuordnung aufgehoben.  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel verwendet `gcnew` zum Zuordnen eines „Message“\-Objekts verwendet.  
  
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
  
  **32**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)