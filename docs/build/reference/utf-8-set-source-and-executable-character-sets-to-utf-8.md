---
title: Utf - 8 (Quelle festlegen und ausführbare Datei legt in UTF-8-Zeichen) | Microsoft Docs
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
- /utf-8
dev_langs:
- C++
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e51db101db10b0461d7e9aa76b62319989d9f7d0
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/UTF-8 (Quelle festlegen und ausführbare Datei Zeichensätze in UTF-8)
Gibt an, der quellzeichensatz, sowohl die ausführungszeichensatz als UTF-8.  
  
## <a name="syntax"></a>Syntax  
  
```  
/utf-8  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die **/utf-8** Option zur Angabe der Quelle und die Ausführung Zeichensätze wie mithilfe von UTF-8 codiert. Dies ist äquivalent zum Angeben von **/source-Charset:utf-8 /execution-Charset:utf-8** in der Befehlszeile angegeben. Diese Optionen auch ermöglicht die **/validate-charset** standardmäßig die Option. Eine Liste der unterstützten Codepage-IDs und Namen von Zeichen festlegen, finden Sie unter [Codepage-IDs](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 Standardmäßig erkennt Visual Studio eine Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in eine codierte Unicode-Format, z. B. UTF-16 bzw. UTF-8 ist. Wenn keine Bytereihenfolge-Marke gefunden wird, es geht davon aus, sofern Sie mithilfe eine Codepage angegeben haben, wird die Quelldatei codiert mithilfe der aktuellen Codepage Benutzer **/utf-8** oder **/source-charset** Option. Visual Studio können Sie C++-Quellcode mithilfe einer von mehreren zeichencodierungen zu speichern. Weitere Informationen zu Quell- und ausführungszeichensätze, finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der sprachdokumentation.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.  
  
3.  In **erweiterte Optionen**, Hinzufügen der **/utf-8** aus, und geben Sie Ihre bevorzugten Codierung.  
  
4.  Wählen Sie **OK** zum Speichern der Änderungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/Execution-CharSet (Festlegen der Ausführung-Zeichensatz)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/Source-CharSet (Festlegen der Quell-Zeichensatz)](../../build/reference/source-charset-set-source-character-set.md)   
 [/validate-charset (Auf kompatible Zeichen überprüfen)](../../build/reference/validate-charset-validate-for-compatible-characters.md)