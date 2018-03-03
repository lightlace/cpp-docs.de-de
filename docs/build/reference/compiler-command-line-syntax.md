---
title: "Syntax für die Compilerbefehlszeile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7fb89aca1990d44d7ef62ea76788b38e8ffa1d6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-command-line-syntax"></a>Syntax für die Compilerbefehlszeile
CL-Befehlszeile wird die folgende Syntax verwendet:  
  
```  
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]  
```  
  
 Die folgende Tabelle beschreibt die Eingabe in der CL-Befehl.  
  
|Eingabe|Bedeutung|  
|-----------|-------------|  
|*Option*|Eine oder mehrere [CL-Optionen](../../build/reference/compiler-options.md). Beachten Sie, dass alle Optionen für alle angegebenen Quelldateien gelten. Optionen werden von einem Schrägstrich (/) oder einen Bindestrich (-) angegeben. Wenn eine Option Argument die Option Beschreibung Dokumente annimmt, ob ein Leerzeichen zwischen der Option und die Argumente zulässig ist. Optionsnamen (außer der/Help-Option) sind Groß-/Kleinschreibung beachtet. Finden Sie unter [Reihenfolge von CL-Optionen](../../build/reference/order-of-cl-options.md) für Weitere Informationen.|  
|`file`|Der Name der ein oder mehrere Quelldateien, OBJ-Dateien oder Bibliotheken. Kompiliert Quelldateien "CL" und die Namen der OBJ-Dateien und Bibliotheken an dem Linker übergeben. Finden Sie unter [Syntax für Dateinamen bei CL](../../build/reference/cl-filename-syntax.md) für Weitere Informationen.|  
|*LIB*|Eine oder mehrere Bibliotheksnamen. CL übergibt diese Namen an den Linker.|  
|*Befehlsdatei*|Eine Datei, die mehrere Optionen und Dateinamen enthält. Finden Sie unter [CL-Befehlsdateien](../../build/reference/cl-command-files.md) für Weitere Informationen.|  
|*Link-opt*|Eine oder mehrere [Optionen des Linkers](../../build/reference/linker-options.md). CL übergibt diese Optionen an den Linker.|  
  
 Sie können eine beliebige Anzahl von Optionen, Dateinamen und Bibliotheksnamen angeben, solange die Anzahl der Zeichen in der Befehlszeile 1024, das Limit vorgegeben vom Betriebssystem nicht überschreitet.  
  
 Informationen über den Rückgabewert von cl.exe finden Sie unter [Rückgabewert von cl.exe](../../build/reference/return-value-of-cl-exe.md) .  
  
> [!NOTE]
>  Grenze von 1024 Zeichen für die Eingabe in der Befehlszeile ist nicht unbedingt in zukünftigen Versionen von Windows identisch sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)