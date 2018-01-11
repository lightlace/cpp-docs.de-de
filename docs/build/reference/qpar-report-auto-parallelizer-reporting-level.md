---
title: -Qpar-Report (Auto-Parallelisierer Reporting Stufe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70ae055d69341cc773b8b40ed1111b65ba5683cf
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-report (Auto-Parallelizer-Berichtsebene)
Ermöglicht die Berichtsfunktion des Compilers [Auto-Parallelisierer](../../parallel/auto-parallelization-and-auto-vectorization.md) und gibt die Ebene der informationsmeldungen für die Ausgabe während der Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Qpar-report:{1}{2}  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ Qpar-Bericht: 1**  
 Gibt eine Informationsmeldung für Schleifen an, die parallel ausgeführt werden.  
  
 **/ Qpar-Bericht: 2**  
 Gibt eine Informationsmeldung für Schleifen an, die parallel ausgeführt werden und auch für Schleifen, die nicht, zusammen mit einen Ursachencode parallel ausgeführt werden.  
  
 Nachrichten werden an Stdout gesendet. Wenn keine Informationsmeldungen angezeigt werden, enthält der Code keine Schleifen oder die Berichterstellungsebene wurde nicht festgelegt, um Bericht-Schleifen, die nicht parallel ausgeführt werden, zu melden. Weitere Informationen zu Ursachencodes und Meldungen finden Sie unter [Vectorizer- and Parallelizer-Meldungen](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>So legen Sie die /Qpar-report-Compileroption in Visual Studio fest  
  
1.  Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.  
  
2.  In der **Eigenschaftenseiten** Dialogfeld unter **C/C++-**Option **Befehlszeile**.  
  
3.  In der **Zusatzoptionen** geben `/Qpar-report:1` oder `/Qpar-report:2`.  
  
### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>So legen Sie die Compileroption "/Qpar-report" programmgesteuert fest  
  
-   Verwenden Sie hierzu das Codebeispiel unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Q-Optionen (Operationen auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Parallele Programmierung in systemeigenem Code](http://go.microsoft.com/fwlink/p/?linkid=263662)