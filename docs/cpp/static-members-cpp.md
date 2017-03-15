---
title: "Statische Member (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klasseninstanzen [C++], Freigegebene Member"
  - "Klasseninstanzen [C++], Statische Member"
  - "Klassenmember [C++], Freigegeben"
  - "Klassenmember [C++], static"
  - "Datenmember [C++], Statische Datenmember"
  - "Instanzkonstruktoren, Freigegebene Member"
  - "Instanzkonstruktoren, Statische Member"
  - "Member [C++], Statische Datenmember"
  - "Statische Datenmember [C++]"
  - "Statische Member [C++], Datenmember"
ms.assetid: 9cc8cf0f-d74c-46f2-8e83-42d4e42c8370
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Statische Member (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Klassen können statische Memberdaten und Memberfunktionen enthalten.  Wenn ein Datenmember als **statisch** deklariert ist, wird nur eine Kopie der Daten für alle Objekte der Klasse beibehalten.  Weitere Informationen finden Sie unter [Statische Memberfunktionen](../misc/static-member-functions.md).  
  
 Statische Datenmember sind nicht Teil von Objekten eines angegebenen Klassentyps.  Daher gilt die Deklaration eines statischen Datenmembers nicht als eine Definition.  Der Datenmember wird im Klassenbereich deklariert, die Definition wird jedoch im Dateigültigkeitsbereich ausgeführt.  Diese statischen Member verfügen über eine externe Bindung.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```  
// static_data_members.cpp  
class BufferedOutput  
{  
public:  
   // Return number of bytes written by any object of this class.  
   short BytesWritten()  
   {  
      return bytecount;  
   }  
  
   // Reset the counter.  
   static void ResetCount()  
   {  
      bytecount = 0;  
   }  
  
   // Static member declaration.  
   static long bytecount;  
};  
  
// Define bytecount in file scope.  
long BufferedOutput::bytecount;  
  
int main()  
{  
}  
```  
  
 Im vorangehenden Code ist der `bytecount`\-Member in der `BufferedOutput`\-Klasse deklariert, muss aber außerhalb der Klassendeklaration definiert sein.  
  
 Auf statische Datenmember kann verwiesen werden, ohne dass auf ein Klassentypobjekt verwiesen wird.  Die Anzahl von Bytes, die mithilfe von `BufferedOutput`\-Objekten geschrieben wurden, kann wie folgt abgerufen werden:  
  
```  
long nBytes = BufferedOutput::bytecount;  
```  
  
 Damit der statische Member vorhanden sein kann, ist es nicht notwendig, dass Klassentypobjekte vorhanden sind.  Auf statische Member kann auch mithilfe der Memberauswahloperatoren \(**.** und **–\>**\) zugegriffen werden.  Zum Beispiel:  
  
```  
BufferedOutput Console;  
  
long nBytes = Console.bytecount;  
```  
  
 Im vorangegangenen Fall wird der Verweis auf das Objekt \(`Console`\) nicht ausgewertet. Der zurückgegebene Wert ist der des statischen `bytecount`\-Objekts.  
  
 Statische Datenmember unterliegen Klassenmember\-Zugriffsregeln, sodass ein privater Zugriff auf statische Datenmember nur für Klassenmemberfunktionen und "Friends" zulässig ist.  Diese Regeln sind unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md) beschrieben.  Die Ausnahme besteht darin, dass statische Datenmember im Dateibereich definiert werden müssen, ungeachtet ihrer Zugriffseinschränkungen.  Wenn der Datenmember explizit initialisiert werden soll, muss ein Initialisierer mit der Definition bereitgestellt werden.  
  
 Der Typ eines statischen Members wird nicht durch seinen Klassennamen qualifiziert.  Deshalb ist der Typ von `BufferedOutput::bytecount``long`.  
  
## Siehe auch  
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)