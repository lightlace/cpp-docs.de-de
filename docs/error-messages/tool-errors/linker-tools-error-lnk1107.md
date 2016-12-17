---
title: "Linkertoolfehler LNK1107"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1107"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1107"
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
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