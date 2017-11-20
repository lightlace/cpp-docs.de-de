---
title: Importieren mithilfe von DEF-Dateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 81148525b70f3c5ff351feb9561699f3b9b5e932
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="importing-using-def-files"></a>Importieren mithilfe von DEF-Dateien
Wenn Sie verwenden **von "__declspec(dllimport)" "** zusammen mit einer DEF-Datei, sollten Sie die DEF-Datei, um Daten anstelle von KONSTANTEN verwenden, um die Wahrscheinlichkeit zu reduzieren, dass falsche Codierung Probleme entstehen ändern:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   DATA  
```  
  
 In der folgenden Tabelle wird erläutert, weshalb.  
  
|Stichwort|In der Importbibliothek ausgibt|Exporte|  
|-------------|---------------------------------|-------------|  
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|  
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|  
  
 Mit **von "__declspec(dllimport)" "** und Konstante enthält sowohl die `imp` Version und dem nicht ergänzten Namen in der LIB-DLL-Importbibliothek, die erstellt wird, um die explizite Verknüpfung zu ermöglichen. Mit **von "__declspec(dllimport)" "** und Listen der Daten nur die `imp` Version des Namens.  
  
 Wenn Sie die Konstante verwenden, eines der beiden folgenden Codekonstrukte genutzt werden für den Zugriff auf `ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 - oder -   
  
```  
ULONG *ulDataInDll;      /*prototype*/  
if (*ulDataInDll == 0L)  /*sample code fragment*/  
```  
  
 Allerdings bei Verwendung von Daten in der DEF-Datei nur mit folgender Definition kompiliertem Code kann Zugriff auf die Variable `ulDataInDll`:  
  
```  
__declspec(dllimport) ULONG ulDataInDll;  
  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 Konstante ist mehr gefährlich, da Sie vergessen, die zusätzliche Dereferenzierungsebene verwenden, Sie möglicherweise die importieren Local Address Table-Zeiger auf die Variable zugreifen konnte, nicht auf die Variable selbst. Diese Art von Problem kann häufig als eine zugriffsverletzung manifest, da die importieren Local Address Table derzeit durch den Compiler und Linker schreibgeschützt ist.  
  
 Der aktuelle Visual C++-Linker gibt eine Warnung aus, wenn es erkennt, dass die Konstante in der DEF-Datei für diesen Fall berücksichtigt. Der einzige Grund für die Konstante verwenden wird, wenn einige Objektdatei kann nicht, in dem die Header-Datei nicht aufgeführt neu kompilieren **von "__declspec(dllimport)" "** auf den Prototyp.  
  
## <a name="see-also"></a>Siehe auch  
 [Importieren in eine Anwendung](../build/importing-into-an-application.md)
