---
title: Bereitstellen eine Visual C++-Anwendung mithilfe eines Setupprojekts | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 454507a3a3f33b43af0e50c25dab6703aa75a56b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts
Beschreibt, wie ein Setup-Projekt zu verwenden, um ein Visual C++-Anwendung bereitzustellen.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   Ein Computer mit [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] installiert.  
  
-   Ein zusätzlicher Computer, die über keinen Visual C++-Bibliotheken.  
  
### <a name="to-deploy-an-application-by-using-a-setup-project"></a>Zum Bereitstellen einer Anwendung mithilfe eines Setupprojekts  
  
1.  Verwenden der **MFC ApplicationWizard** um eine neue Visual Studio-Projektmappe zu erstellen. Suchen Sie den Assistenten aus der **neues Projekt** Dialogfeld erweitern Sie die **Visual C++** Knoten **MFC**Option **MFC-Anwendung**, geben Sie eine für das Projekt, und klicken Sie dann auf **OK**.  
  
2.  Ändern Sie die aktive Lösungskonfiguration auf **Version**. Aus der **erstellen** klicken Sie im Menü **Configuration Manger**. Aus der **Configuration Manager** wählen Sie im Dialogfeld **Release** aus der **aktive Projektmappenkonfiguration** Dropdown-Menü.  
  
3.  Drücken Sie F7, um die Anwendung zu erstellen. Alternativ können Sie auf die **erstellen** Menü klicken Sie auf **Projektmappe**. Dadurch wird das Setup-Projekt die Ausgabe dieses Projekts der MFC-Anwendung verwendet.  
  
4.  Laden Sie InstallShield Limited Edition (ISLE), die für Visual Studio-Entwickler kostenlos und ersetzt die Funktionen der Projektvorlagen in Visual Studio für Setup und Bereitstellung herunter, wenn Sie dies nicht bereits getan haben. Wenn Sie mit dem Internet verbunden sind, öffnen Sie die **neues Projekt** Dialogfelds auswählen **Datei**, **neu**, **Projekt** Balken- oder indem im Menü mit der rechten Maustaste der Lösung in **Projektmappen-Explorer** auswählen und **hinzufügen**, **neues Projekt**. Erweitern Sie die **andere Projekttypen** Knoten, wählen Sie **InstallShield Limited Edition aktivieren** in der **Setup und Bereitstellung** Knoten, und befolgen Sie die Anweisungen, die angezeigt werden. Sobald Sie heruntergeladen, installiert und aktiviert die InstallShield Limited Edition, schließen Sie Visual Studio, und öffnen Sie es erneut.  
  
5.  Öffnen der **neues Projekt** (Dialogfeld) erneut aus, erweitern Sie die **andere Projekttypen** Knoten, und wählen Sie **InstallShield Limited Edition-Projekt** in der  **InstallShield Limited Edition** Knoten.  
  
6.  Führen Sie die Anweisungen in der **Einstieg** Knoten des Setup-Projekts erstellt, indem die InstallShield Limited Edition-Vorlage, die einen Ausgabeverweis auf das Visual Studio-MFC-Projekt hinzufügen.  
  
7.  Erstellen Sie das Setupprojekt, um die Installationsdatei (setup.exe) zu erstellen. Zu diesem Zweck mit der rechten Maustaste in den Setup-Projektknoten **Projektmappen-Explorer** , und wählen Sie **erstellen**.  
  
     InstallShield Limited Edition erstellt die Setupdatei, in der Struktur der Setup-Projekt (standardmäßig, es kann werden befindet sich im Unterordner "Express\SingleImage\DiskImages\DISK1" des Setup-Projekts).  
  
8.  Führen Sie das Setup-Programm auf einem zweiten Computer, die über keinen Visual C++-Bibliotheken.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)