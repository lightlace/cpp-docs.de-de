---
title: Linkertoolfehler Lnk1107 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1107
dev_langs: C++
helpviewer_keywords: LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fae412de31163aa1b5248af43227042cd04563ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1107"></a>Linkertoolfehler LNK1107
Ungültige oder beschädigte Datei: an Position kann nicht gelesen werden  
  
 Das Tool konnte die Datei nicht gelesen werden. Erstellen Sie die Datei neu.  
  
 LNK1107 kann auch auftreten, wenn Sie versuchen, ein Modul übergeben (erstellt mit ".dll" oder "netmodule-Erweiterung [/CLR: noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) oder [/noAssembly](../../build/reference/noassembly-create-a-msil-module.md)) an den Linker; stattdessen die OBJ-Datei übergeben.  
  
 Wenn Sie im folgende Beispiel kompilieren:  
  
```  
// LNK1107.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 und geben Sie dann **verknüpfen LNK1107.dll** erhalten Sie in der Befehlszeile LNK1107.  Geben Sie zum Beheben des Fehlers **verknüpfen LNK1107.obj** stattdessen.