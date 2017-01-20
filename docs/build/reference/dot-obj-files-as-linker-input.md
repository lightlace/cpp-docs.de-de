---
title: ".OBJ-Dateien als Linkereingabe"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".obj-Dateien als Linkereingabe"
  - "COFF-Dateien"
  - "LINK-Tool [C++], .obj-Dateien"
  - "Linker [C++], OBJ-Dateien als Eingabe"
  - "OBJ-Dateien als Linkereingabe"
  - "Objektdateien, Linkerausgabe"
  - "OMF-Objektdateien"
ms.assetid: 3028e423-8b10-4972-8eb4-6e9ae58f0a26
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# .OBJ-Dateien als Linkereingabe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Linkertool \(LINK.EXE\) akzeptiert OBJ\-Dateien im Format COFF \(Common Object File Format\).  
  
## Hinweise  
 Microsoft stellt ein Dokument mit einer Definition des COFF\-Formats zum Download bereit.  Weitere Informationen, Downloadrevision 8.1 oder höher aus [Microsoft\-PE\-Datei und Common Object File Format\-Spezifikation](http://go.microsoft.com/fwlink/?LinkId=93292).  
  
## Unterstützung für Unicode  
 Beginnend mit Visual Studio 2005 unterstützt der Microsoft Visual C\+\+\-Compiler Unicode\-Zeichen in Bezeichnern entsprechend den Standards ISO\/IEC C und C\+\+.  Frühere Versionen des Compilers haben nur ASCII\-Zeichen in Bezeichnern unterstützt.  Um Unicode in Namen von Funktionen, Klassen und statischen Feldern zu unterstützen, verwenden der Compiler und der Linker die Unicode\-Codierung UTF\-8 für COFF\-Symbole in OBJ\-Dateien.  Die UTF\-8\-Codierung ist mit der von früheren Versionen von Visual Studio verwendeten ASCII\-Codierung kompatibel.  
  
 Weitere Informationen zum Compiler und Linker finden Sie unter [Unicode\-Unterstützung im Compiler und Linker](../../build/reference/unicode-support-in-the-compiler-and-linker.md).  Weitere Informationen zum Unicode\-Standard, finden Sie die [Unicode](http://go.microsoft.com/fwlink/?LinkId=37123) Organisation.  
  
## Siehe auch  
 [LINK\-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [Unterstützung für Unicode](../../text/support-for-unicode.md)   
 [Unicode\-Unterstützung im Compiler und Linker](../../build/reference/unicode-support-in-the-compiler-and-linker.md)   
 [Unicode\-Standard](http://go.microsoft.com/fwlink/?LinkId=37123)   
 [Common Object File Format\-Spezifikation](http://go.microsoft.com/fwlink/?LinkId=93292)