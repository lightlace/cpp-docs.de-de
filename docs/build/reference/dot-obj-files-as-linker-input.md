---
title: . OBJ-Dateien als Linkereingabe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
ms.assetid: 3028e423-8b10-4972-8eb4-6e9ae58f0a26
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ca8346f9ff29d097450eda4d8bfbfee7f7a3f522
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="obj-files-as-linker-input"></a>.OBJ-Dateien als Linkereingabe
Der Linkertool (LINK. EXE-Datei) akzeptiert OBJ-Dateien, die im Common Object File Format (COFF).  
  
## <a name="remarks"></a>Hinweise  
 Microsoft stellt eine herunterladbare Dokument, das allgemeine Objekt Dateiformat definiert. Weitere Informationen herunterladen Version 8.1 oder höher von der [Microsoft übertragbare ausführbare Datei und Common Object File Format Specification](http://go.microsoft.com/fwlink/?LinkId=93292).  
  
## <a name="unicode-support"></a>Unterstützung für Unicode  
 Ab Visual Studio 2005 werden unterstützt Microsoft Visual C++-Compiler Unicode-Zeichen in Bezeichnern gemäß der Definition von ISO/IEC C- und C++-Standards. Ältere Versionen des Compilers unterstützt nur ASCII-Zeichen in Bezeichnern. Verwenden zur Unterstützung von Unicode in die Namen der Funktionen, Klassen und statische Variablen Compiler und Linker Unicode-UTF-8-Codierung für COFF-Symbole in der OBJ-Dateien. UTF-8-Codierung ist kompatibel mit der ASCII-Codierung, die von früheren Versionen von Visual Studio verwendet.  
  
 Weitere Informationen zu den Compiler und Linker finden Sie unter [Unicode-Unterstützung im Compiler und Linker](../../build/reference/unicode-support-in-the-compiler-and-linker.md). Weitere Informationen zu den Unicode-Standard, finden Sie unter der [Unicode](http://go.microsoft.com/fwlink/?LinkId=37123) Organisation.  
  
## <a name="see-also"></a>Siehe auch  
 [LINK-Eingabedateien](../../build/reference/link-input-files.md)   
 [Optionen des Linkers](../../build/reference/linker-options.md)   
 [Unterstützung für Unicode](../../text/support-for-unicode.md)   
 [Unicode-Unterstützung im Compiler und Linker](../../build/reference/unicode-support-in-the-compiler-and-linker.md)   
 [Unicode-standard](http://go.microsoft.com/fwlink/?LinkId=37123)   
 [Common Object File Format Specification](http://go.microsoft.com/fwlink/?LinkId=93292)