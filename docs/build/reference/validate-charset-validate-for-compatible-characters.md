---
title: -Überprüfen-Zeichensatz (Validate für kompatible Zeichen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /validate-charset
- validate-charset
dev_langs:
- C++
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e82b9fd42b636cffd318f6327cc064687334329
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/Validate-CharSet (Validate für kompatible Zeichen)
Überprüft, ob die Datei Quelltext darstellbaren nur Zeichen enthält als UTF-8.  
  
## <a name="syntax"></a>Syntax  
  
```  
/validate-charset[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die **/validate-charset** Option, um sicherzustellen, dass der Quellcode enthält nur die Zeichen, die in beiden quellzeichensatzes dargestellt werden können und ausführungszeichensatz festgelegt. Diese Überprüfung wird automatisch aktiviert, bei der Angabe **/source-charset**, **/execution-charset**, oder **/utf-8** Compileroptionen. Sie können diese Prüfung explizit deaktivieren, durch Angeben der **/ validate-Charset -** Option.  
  
 Standardmäßig erkennt Visual Studio eine Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in eine codierte Unicode-Format, z. B. UTF-16 bzw. UTF-8 ist. Wenn keine Bytereihenfolge-Marke gefunden wird, es geht davon aus, sofern Sie mithilfe eine Codepage angegeben haben, wird die Quelldatei codiert mithilfe der aktuellen Codepage Benutzer **/utf-8** oder **/source-charset** Option. Visual Studio können Sie C++-Quellcode mithilfe einer von mehreren zeichencodierungen zu speichern. Weitere Informationen zu Quell- und ausführungszeichensätze, finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der sprachdokumentation. Eine Liste der unterstützten Codepage-IDs und Namen von Zeichen festlegen, finden Sie unter [Codepage-IDs](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 Visual Studio verwendet UTF-8 als die internen zeichencodierung während der Konvertierung zwischen den Quell- und ausführungszeichensatz. Wenn ein Zeichen in der Quelldatei im ausführungszeichensatz dargestellt werden kann, ersetzt die UTF-8-Konvertierung durch ein Fragezeichen ersetzt ein "?" Zeichen. Die **/validate-charset** Option bewirkt, dass die Kompilierung eine Warnung gemeldet wird, ist dies der Fall.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.  
  
3.  In **erweiterte Optionen**, Hinzufügen der **/validate-charset** aus, und geben Sie Ihre bevorzugten Codierung.  
  
4.  Wählen Sie **OK** zum Speichern der Änderungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/Execution-CharSet (Festlegen der Ausführung-Zeichensatz)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/Source-CharSet (Festlegen der Quell-Zeichensatz)](../../build/reference/source-charset-set-source-character-set.md)   
 [/utf-8 (Quelle und ausführbare Zeichensätze auf UTF-8 festlegen)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)