---
title: -Qvec-Report (Auto-Vektorisierer Reporting Stufe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 43c9a182046ff148621151107a98932cc39835f2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (Auto-Vectorizer-Berichtsebene)
Ermöglicht die Berichtsfunktion des Compilers [Auto-Vektorisierer](../../parallel/auto-parallelization-and-auto-vectorization.md) und gibt die Ebene der informationsmeldungen für die Ausgabe während der Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Qvec-report:{1}{2}  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ Qvec-Report: 1**  
 Gibt eine informationsmeldung für Schleifen, die vektorisiert werden.  
  
 **/ Qvec-Bericht: 2**  
 Gibt eine informationsmeldung für Schleifen, die vektorisiert werden und for-Schleifen, die nicht, zusammen mit einen Ursachencode vektorisiert werden.  
  
 Informationen zu Ursachencodes und Meldungen finden Sie unter [Vectorizer- and Parallelizer-Meldungen](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>So legen Sie die /Qvec-report-Compileroption in Visual Studio fest  
  
1.  Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.  
  
2.  In der **Eigenschaftenseiten** Dialogfeld unter **C/C++-**Option **Befehlszeile**.  
  
3.  In der **Zusatzoptionen** geben `/Qvec-report:1` oder `/Qvec-report:2`.  
  
### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>So legen Sie die /Qvec-report-Compileroption programmgesteuert fest  
  
-   Verwenden Sie hierzu das Codebeispiel unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Q-Optionen (Operationen auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Parallele Programmierung in systemeigenem Code](http://go.microsoft.com/fwlink/p/?linkid=263662)