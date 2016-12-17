---
title: "Importieren von Daten mithilfe von &quot;__declspec(dllimport)&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport)-Schlüsselwort [C++]"
  - "dllimport-Attribut [C++], Datenimporte"
  - "Importieren von Daten [C++]"
  - "Importieren von DLLs [C++], __declspec(dllimport)"
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Importieren von Daten mithilfe von &quot;__declspec(dllimport)&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im Fall von Daten bietet die Verwendung von **\_\_declspec\(dllimport\)** eine bequeme Möglichkeit, eine Ebene von Zeigeroperationen zu umgehen.  Wenn Sie Daten aus einer DLL importieren, müssen Sie noch die Importadressentabelle durchlaufen.  Vor **\_\_declspec\(dllimport\)** hatte dies zur Folge, dass beim Zugriff auf die aus der DLL exportierten Daten eine zusätzliche Ebene von Zeigeroperationen implementiert werden musste:  
  
```  
// project.h  
#ifdef _DLL   // If accessing the data from inside the DLL  
   ULONG ulDataInDll;  
  
#else         // If accessing the data from outside the DLL  
   ULONG *ulDataInDll;  
#endif  
```  
  
 Anschließend wurden die Daten aus der DEF\-Datei exportiert:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   CONSTANT  
```  
  
 Der Zugriff fand außerhalb der DLL statt:  
  
```  
if (*ulDataInDll == 0L)   
{  
   // Do stuff here  
}  
```  
  
 Wenn Sie die Daten mit **\_\_declspec\(dllimport\)** kennzeichnen, wird der Code für Zeigeroperationen automatisch vom Compiler generiert.  Die oben genannten Schritte entfallen einfach.  Wie bereits erwähnt, sollten Sie keine **\_\_declspec\(dllimport\)**\-Deklaration für Daten verwenden, während die DLL erstellt wird.  Die Funktionen innerhalb der DLL verwenden keine Importadressentabelle für den Zugriff auf das Datenobjekt. Es ist also keine zusätzliche Ebene von Zeigeroperationen vorhanden.  
  
 Um die Daten automatisch aus der DLL zu exportieren, verwenden Sie die folgende Deklaration:  
  
```  
__declspec(dllexport) ULONG ulDataInDLL;  
```  
  
## Siehe auch  
 [Importieren in eine Anwendung](../build/importing-into-an-application.md)