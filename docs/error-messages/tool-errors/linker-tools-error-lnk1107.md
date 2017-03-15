---
title: "Linkertoolfehler LNK1107 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1107"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1107"
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Linkertoolfehler LNK1107
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Ungültige oder beschädigte Datei: Lesen bei**   
 ***Position* nicht möglich**  
  
 Das Tool konnte die Datei nicht lesen.  Erstellen Sie die Datei neu.  
  
 LNK1107 könnte auch auftreten, wenn Sie versuchen, ein Modul \(.dll\- oder .netmodule\-Erweiterung mit [\/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) oder [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) erstellt\) an den Linker übergeben; Führen Sie stattdessen die OBJ\-Datei.  
  
 Wenn Sie das folgende Beispiel kompilieren:  
  
```  
// LNK1107.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 und dann in der Befehlszeile **link LNK1107.dll** angeben, erhalten Sie den Fehler LNK1107.  Um den Fehler zu beheben, geben Sie stattdessen **link LNK1107.obj** an.