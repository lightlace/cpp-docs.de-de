---
title: Syntax für die Compilerbefehlszeile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 825121a111d47de6b012aad444907363ad8c2a36
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370120"
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
|*lib*|Eine oder mehrere Bibliotheksnamen. CL übergibt diese Namen an den Linker.|  
|*Befehlsdatei*|Eine Datei, die mehrere Optionen und Dateinamen enthält. Finden Sie unter [CL-Befehlsdateien](../../build/reference/cl-command-files.md) für Weitere Informationen.|  
|*Link-opt*|Eine oder mehrere [Optionen des Linkers](../../build/reference/linker-options.md). CL übergibt diese Optionen an den Linker.|  
  
 Sie können eine beliebige Anzahl von Optionen, Dateinamen und Bibliotheksnamen angeben, solange die Anzahl der Zeichen in der Befehlszeile 1024, das Limit vorgegeben vom Betriebssystem nicht überschreitet.  
  
 Informationen über den Rückgabewert von cl.exe finden Sie unter [Rückgabewert von cl.exe](../../build/reference/return-value-of-cl-exe.md) .  
  
> [!NOTE]
>  Grenze von 1024 Zeichen für die Eingabe in der Befehlszeile ist nicht unbedingt in zukünftigen Versionen von Windows identisch sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)