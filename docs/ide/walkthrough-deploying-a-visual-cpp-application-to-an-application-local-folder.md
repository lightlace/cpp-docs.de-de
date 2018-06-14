---
title: Bereitstellen einer Visual C++-Anwendung in einem lokalen Anwendungsordner | Microsoft-Dokumentation
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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337908"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung in einem lokalen Anwendungsordner
In diesem Artikel wird beschrieben, wie eine Visual C++-Anwendung durch Kopieren von Dateien in den Ordner bereitgestellt wird.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   Einen Computer, auf dem Visual Studio installiert ist.  
  
-   Einen zusätzlichen Computer, auf dem keine Visual C++-Bibliotheken vorhanden sind.  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>So stellen Sie eine Anwendung in einem lokalen Anwendungsordner bereit  
  
1.  Erstellen Sie eine MFC-Anwendung, indem Sie die folgenden Schritte unter [Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md) befolgen.  
  
2.  Kopieren Sie die entsprechende MFC- und C-Laufzeitbibliotheksdateien (CRT), und fügen Sie diese in den Ordner „\Release\“ Ihres MFC-Projekts ein. Kopieren Sie beispielsweise „mfc100u.dll“ und „msvcr100.dll“ aus \Programme\Microsoft Visual Studio 10.0\VC\redist\x86\ für eine x86-Plattform- und Unicode-Unterstützung. Weitere Informationen über andere Dateien, die Sie möglicherweise kopieren müssen, finden Sie unter [Determining Which DLLs to Redistribute (Ermitteln der zu verteilenden DLLs)](../ide/determining-which-dlls-to-redistribute.md).  
  
3.  Führen Sie die MFC-Anwendung auf einem zweiten Computer aus, der über keine der Visual C++-Bibliotheken verfügt.  
  
    1.  Kopieren Sie die Inhalte des Ordners „\Release\“, und fügen Sie sie in den Anwendungsordner auf dem zweiten Computer ein.  
  
    2.  Führen Sie die Anwendung auf dem zweiten Computer aus.  
  
     Die Anwendung wird erfolgreich ausgeführt, da die Visual C++-Bibliotheken im lokalen Anwendungsordner verfügbar sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)