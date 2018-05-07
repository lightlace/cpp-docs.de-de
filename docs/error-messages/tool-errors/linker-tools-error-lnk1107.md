---
title: Linkertoolfehler Lnk1107 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1107
dev_langs:
- C++
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fee2105cb0c12287cd2b47636f0e47011854a608
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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