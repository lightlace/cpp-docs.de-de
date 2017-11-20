---
title: -Quelle-Zeichensatz (Quellzeichensatz Satz) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- source-charset
- /source-charset
dev_langs: C++
helpviewer_keywords: /execution-charset compiler option
ms.assetid: d3c5bf7f-526d-4ee4-acc5-c1a02a4fc481
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 33e02b645d13c848c9cb9b3a5d082ccf05960433
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="source-charset-set-source-character-set"></a>/Source-CharSet (Festlegen der Quell-Zeichensatz)
Ermöglicht die Angabe den quellzeichensatz für die ausführbare Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
/source-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>Argumente  
 **IANA_name**  
 IANA definierte Zeichensatzes Name des.  
  
 **CPID**  
 Der Codepagebezeichner als Dezimalzahl.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die **/source-charset** Option zur Angabe einer erweiterten quellzeichensatz verwenden, wenn Ihre Quelldateien enthalten Zeichen, die nicht dargestellt werden, in der einfachen quellzeichensatzes. Der quellzeichensatz ist die Codierung für den Quelltext des Programms in die interne Darstellung verwendet als Eingabe für den vorverarbeitungsphasen vor der Kompilierung zu interpretieren. Die interne Darstellung wird dann in die ausführungszeichengruppe zum Speichern von Zeichenfolgen und Werte in die ausführbare Datei konvertiert. Können Sie entweder die IANA Name des Zeichensatzes ISO oder ein Punkt (.) gefolgt von einer 3 bis 5 Ziffern decimal Codepage-Bezeichner der zu verwendenden Zeichensatz angeben. Eine Liste der unterstützten Codepage-IDs und Namen von Zeichen festlegen, finden Sie unter [Codepage-IDs](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 Standardmäßig erkennt Visual Studio eine Bytereihenfolge-Marke, um festzustellen, ob die Quelldatei in eine codierte Unicode-Format, z. B. UTF-16 bzw. UTF-8 ist. Wenn keine Bytereihenfolge-Marke gefunden wird, es geht davon aus die Quelldatei wird codiert mithilfe der aktuelle Benutzer-Codepage, außer Sie einen Zeichensatz Namen oder die Codepage geben mithilfe der **/source-charset** Option. Visual Studio können Sie C++-Quellcode mithilfe einer von mehreren zeichencodierungen zu speichern. Weitere Informationen zu Quell- und ausführungszeichensätze, finden Sie unter [Zeichensätze](../../cpp/character-sets2.md) in der sprachdokumentation.  
  
 Der quellzeichensatz, das Sie angeben muss die 7-Bit-ASCII-Zeichen, die dieselben Codepunkte in Ihre Zeichensatz zuordnen, oder viele Kompilierungsfehler enthält sind befolgen. Der quellzeichensatz muss auch sämtliche in den erweiterten Unicode-Zeichensatz Sicherheitsrichtlinienverwendung von UTF-8. Zeichen, die nicht in UTF-8 Sicherheitsrichtlinienverwendung sind, werden durch eine implementierungsspezifische Substitute dargestellt. Der Microsoft-Compiler verwendet ein Fragezeichen ersetzt diese Zeichen.  
  
 Wenn Sie sowohl die Quell- und ausführungszeichensatz in UTF-8 festlegen möchten, können Sie mithilfe der **/utf-8** Compileroption als Verknüpfung. Dies ist äquivalent zum Angeben von **/source-Charset:utf-8 /execution-Charset:utf-8** in der Befehlszeile angegeben. Diese Optionen auch ermöglicht die **/validate-charset** standardmäßig die Option.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile** Ordner.  
  
3.  In **erweiterte Optionen**, Hinzufügen der **/source-charset** aus, und geben Sie Ihre bevorzugten Codierung.  
  
4.  Wählen Sie **OK** zum Speichern der Änderungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [/Execution-CharSet (Festlegen der Ausführung-Zeichensatz)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/UTF-8 (Quelle festlegen und ausführbare Datei Zeichensätze in UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/Validate-CharSet (Validate für kompatible Zeichen)](../../build/reference/validate-charset-validate-for-compatible-characters.md)