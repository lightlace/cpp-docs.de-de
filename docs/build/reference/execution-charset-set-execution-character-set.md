---
title: -Ausführung-Zeichensatz (Ausführungszeichensatz Satz) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- execution-charset
- /execution-charset
dev_langs:
- C++
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bffe1e39aa181a6d53784fbb4501bf8f662b221
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375951"
---
# <a name="execution-charset-set-execution-character-set"></a>/Execution-CharSet (Festlegen der Ausführung-Zeichensatz)
Können Sie den ausführungszeichensatz für die ausführbare Datei angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
/execution-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>Argumente  
 **IANA_name**  
 IANA definierte Zeichensatzes Name des.  
  
 **CPID**  
 Der Codepagebezeichner.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die **/execution-charset** Option aus, um eine ausführungszeichensatz angeben. Die ausführungszeichengruppe ist die Codierung für den Text des Programms, die in der vorverarbeitung nachdem alle Schritte in der Kompilierungsphase eingegeben wird. Dieser Zeichensatz wird für die interne Darstellung des alle Zeichenfolgen- oder Zeichenliteralen im kompilierten Code verwendet. Legen Sie diese Option aus, geben Sie die erweiterten ausführungszeichensatzes zu verwendende Quelldateien Zeichen enthalten, die nicht im grundlegenden ausführungszeichensatz darstellbar sind. Können Sie entweder die IANA Name des Zeichensatzes ISO oder ein Punkt (.) gefolgt von einer 3 bis 5 Ziffern decimal Codepage-Bezeichner der zu verwendenden Zeichensatz angeben. Eine Liste der unterstützten Codepage-IDs und Namen von Zeichen festlegen, finden Sie unter [Codepage-IDs](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 Standardmäßig erkennt Visual Studio eine Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in eine codierte Unicode-Format, z. B. UTF-16 bzw. UTF-8 ist. Wenn keine Bytereihenfolge-Marke gefunden wird, es geht davon aus die Quelldatei wird codiert mit der aktuellen Codepage Benutzer, sofern Sie angegeben haben, ein Zeichensatz Namen oder die Codepage mithilfe der **/source-charset** Option oder der **/utf-8** Option. Visual Studio können Sie C++-Quellcode mithilfe einer von mehreren zeichencodierungen zu speichern. Weitere Informationen zu Quell- und ausführungszeichensätze, finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der sprachdokumentation.  
  
 Wenn Sie sowohl die Quell- und ausführungszeichensatz in UTF-8 festlegen möchten, können Sie mithilfe der **/utf-8** Compileroption als Verknüpfung. Dies ist äquivalent zum Angeben von **/source-Charset:utf-8 /execution-Charset:utf-8** in der Befehlszeile angegeben. Diese Optionen auch ermöglicht die **/validate-charset** standardmäßig die Option.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.  
  
3.  In **erweiterte Optionen**, Hinzufügen der **/execution-charset** aus, und geben Sie Ihre bevorzugten Codierung.  
  
4.  Wählen Sie **OK** zum Speichern der Änderungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/Source-CharSet (Festlegen der Quell-Zeichensatz)](../../build/reference/source-charset-set-source-character-set.md)   
 [/UTF-8 (Quelle festlegen und ausführbare Datei Zeichensätze in UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/validate-charset (Auf kompatible Zeichen überprüfen)](../../build/reference/validate-charset-validate-for-compatible-characters.md)