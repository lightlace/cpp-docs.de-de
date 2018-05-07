---
title: Bereitstellen einer Visual C++-Anwendung in eine App lokalen Anwendungsordner | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a02e585dc2b82c8b8ad675907e4205db6ad7279
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung in einem lokalen Anwendungsordner
Beschreibt das Bereitstellen einer Visual C++-Anwendung durch Kopieren von Dateien in den Ordner.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   Ein Computer, der Visual Studio installiert ist.  
  
-   Einem anderen Computer, die über keinen Visual C++-Bibliotheken.  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Zum Bereitstellen einer Anwendung auf einem lokalen Anwendungsordner  
  
1.  Erstellen Sie eine MFC-Anwendung mithilfe der Schritte in [Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
2.  Kopieren Sie die entsprechenden Dateien für MFC- und C-Laufzeit (CRT)-Bibliothek – z. B. für x X86 Plattform und Unicode-Unterstützung, kopieren "mfc100u.dll" und "Msvcr100.dll" aus \Programme\Microsoft Visual Studio 10.0\VC\redist\x86\—and fügen Sie sie im Ordner "\Release\" von Das MFC-Projekt. Weitere Informationen zu anderen Dateien, die Sie kopieren können, finden Sie unter [Ermitteln der neu zu verteilenden DLLs](../ide/determining-which-dlls-to-redistribute.md).  
  
3.  Führen Sie die MFC-Anwendung auf einem zweiten Computer, die über keinen Visual C++-Bibliotheken.  
  
    1.  Kopieren Sie den Inhalt des Ordners \Release\, und fügen Sie sie in den Ordner der Anwendung auf dem zweiten Computer.  
  
    2.  Führen Sie die Anwendung auf dem zweiten Computer.  
  
     Die Anwendung wird erfolgreich ausgeführt, da Visual C++-Bibliotheken in der lokalen Anwendungsordner verfügbar sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)