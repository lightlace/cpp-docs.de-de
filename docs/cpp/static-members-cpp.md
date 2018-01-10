---
title: Statische Member (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- class members [C++], static
- instance constructors, static members
- class members [C++], shared
- members [C++], static data members
- static members [C++], data members
- static data members [C++]
- data members [C++], static data members
- class instances [C++], shared members
- instance constructors, shared members
- class instances [C++], static members
ms.assetid: 9cc8cf0f-d74c-46f2-8e83-42d4e42c8370
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0d19985271648e66aa86946c685608f805b1dfe1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="static-members-c"></a>Statische Member (C++)
Klassen können statische Memberdaten und Memberfunktionen enthalten. Wenn ein Datenmember deklariert wird, als **statische**, nur eine Kopie der Daten wird für alle Objekte der Klasse beibehalten.
  
 Statische Datenmember sind nicht Teil von Objekten eines angegebenen Klassentyps. Daher gilt die Deklaration eines statischen Datenmembers nicht als eine Definition. Der Datenmember wird im Klassenbereich deklariert, die Definition wird jedoch im Dateigültigkeitsbereich ausgeführt. Diese statischen Member verfügen über eine externe Bindung. Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
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
  
 Im vorangehenden Code ist der `bytecount`-Member in der `BufferedOutput`-Klasse deklariert, muss aber außerhalb der Klassendeklaration definiert sein.  
  
 Auf statische Datenmember kann verwiesen werden, ohne dass auf ein Klassentypobjekt verwiesen wird. Die Anzahl von Bytes, die mithilfe von `BufferedOutput`-Objekten geschrieben wurden, kann wie folgt abgerufen werden:  
  
```  
long nBytes = BufferedOutput::bytecount;  
```  
  
 Damit der statische Member vorhanden sein kann, ist es nicht notwendig, dass Klassentypobjekte vorhanden sind. Statische Member können auch mithilfe der memberauswahloperatoren zugegriffen werden (**.** und  **->** ) Operatoren. Zum Beispiel:  
  
```  
BufferedOutput Console;  
  
long nBytes = Console.bytecount;  
```  
  
 Im vorangegangenen Fall wird der Verweis auf das Objekt (`Console`) nicht ausgewertet. Der zurückgegebene Wert ist der des statischen `bytecount`-Objekts.  
  
 Statische Datenmember unterliegen Klassenmember-Zugriffsregeln, sodass ein privater Zugriff auf statische Datenmember nur für Klassenmemberfunktionen und "Friends" zulässig ist. Diese Regeln werden beschrieben [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md). Die Ausnahme besteht darin, dass statische Datenmember im Dateibereich definiert werden müssen, ungeachtet ihrer Zugriffseinschränkungen. Wenn der Datenmember explizit initialisiert werden soll, muss ein Initialisierer mit der Definition bereitgestellt werden.  
  
 Der Typ eines statischen Members wird nicht durch seinen Klassennamen qualifiziert. Deshalb ist der Typ von `BufferedOutput::bytecount``long`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)