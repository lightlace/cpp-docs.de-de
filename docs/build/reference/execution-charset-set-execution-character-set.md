---
title: -Execution-Charset (Ausführungszeichensatz festlegen) | Microsoft-Dokumentation
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
ms.openlocfilehash: 02f3e4273e9fc4064b26c6e32d708c4e6d586ae1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212671"
---
# <a name="execution-charset-set-execution-character-set"></a>/ Execution-CharSet (Ausführungszeichensatz festlegen)
Können Sie die ausführungszeichensatzes für die ausführbare Datei angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
/execution-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>Argumente  
 **IANA_name**  
 Der IANA-definierten Zeichensatzname.  
  
 **CPID**  
 Der Codepagebezeichner.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die **/Execution-CharSet** verwenden, um eine ausführungszeichensatzes anzugeben. Die ausführungszeichengruppe ist die Codierung für den Text des Programms, die in der Kompilierungsphase vorverarbeitung nachdem alle Schritte eingegeben wird. Dieser Zeichensatz wird für die interne Darstellung jeder Zeichenfolgen- oder Zeichenliteralen im kompilierten Code verwendet. Legen Sie diese Option aus, geben Sie die erweiterten ausführungszeichensatzes verwenden, wenn Ihre Quelldateien Zeichen enthalten, die nicht im grundlegenden ausführungszeichensatz dargestellt werden kann. Können Sie entweder die IANA Name des Zeichensatzes ISO oder ein Punkt (.) gefolgt von einer 3 bis 5 Ziffern decimal-Codepagebezeichner der zu verwendenden Zeichensatz angeben. Eine Liste der unterstützten Codepage-IDs und Namen der Zeichensatz, finden Sie unter [Codepage-IDs](/windows/desktop/Intl/code-page-identifiers).  
  
 Standardmäßig erkennt Visual Studio eine Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in eine codierte Unicode-Format, z. B. UTF-16 oder UTF-8 ist. Wenn keine Bytereihenfolge-Marke befindet, es geht davon aus die Quelldatei mit der aktuellen Codepage für Benutzer, es sei denn, die Sie angegeben haben, einen Character set, Name oder die Codepage mit ist codiert die **/Source-CharSet** Option oder die **/utf-8** Option. Visual Studio können Sie C++-Quellcode mithilfe der verschiedenen zeichencodierungen zu speichern. Weitere Informationen zu Quell- und ausführungszeichensätze, finden Sie unter [Zeichensätze](../../cpp/character-sets.md) in der Dokumentation zur Sprache.  
  
 Wenn Sie sowohl die Quell- und ausführungszeichensatz in UTF-8 festlegen möchten, können Sie mithilfe der **/utf-8** Compileroption als Kurzform. Dies ist äquivalent zum Angeben von **/source-Charset:utf-8 /execution-Charset:utf-8** in der Befehlszeile. Diese Optionen auch ermöglicht die **/Validate-CharSet** standardmäßig die Option.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.  
  
3.  In **erweiterte Optionen**, Hinzufügen der **/Execution-CharSet** aus, und geben Sie Ihre bevorzugten Codierung.  
  
4.  Wählen Sie **OK** zum Speichern der Änderungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/ Source-CharSet (Quellzeichensatz festlegen)](../../build/reference/source-charset-set-source-character-set.md)   
 [/UTF-8 (Quelle festlegen und ausführbare Zeichensätze auf UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/validate-charset (Auf kompatible Zeichen überprüfen)](../../build/reference/validate-charset-validate-for-compatible-characters.md)