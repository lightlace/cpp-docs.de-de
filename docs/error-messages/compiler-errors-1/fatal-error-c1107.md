---
title: "Schwerwiegender Fehler C1107 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1107"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1107"
ms.assetid: 541a4d9f-10bc-4dd8-b68e-15e548f3dc0a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schwerwiegender Fehler C1107
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Assembly 'Datei' wurde nicht gefunden: Geben Sie den Assemblysuchpfad an, indem Sie \/AI verwenden oder die Umgebungsvariable LIBPATH festlegen  
  
 An eine [\#using](../../preprocessor/hash-using-directive-cpp.md)\-Direktive wurde eine Datei mit Metadaten übergeben, die vom Compiler nicht gefunden wurde.  
  
 **LIBPATH**, die unter dem Thema zu `#using` beschriebene Umgebungsvariable, und die [\/AI](../../build/reference/ai-specify-metadata-directories.md)\-Compileroption ermöglichen es Ihnen, Verzeichnisse festzulegen, in denen der Compiler nach referenzierten Metadateien sucht.