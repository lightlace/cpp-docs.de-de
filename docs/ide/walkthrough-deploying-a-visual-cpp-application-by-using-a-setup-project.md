---
title: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts | Microsoft-Dokumentation
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
ms.openlocfilehash: 36aad914fc9552cea06eabd0898fe33b9b09481e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605830"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts
In diesem Artikel wird beschrieben, wie Sie ein Setup-Projekt verwenden, um eine Visual C++-Anwendung bereitzustellen.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   Ein Computer, auf dem Visual Studio 2012 installiert ist.  
  
-   Einen zusätzlichen Computer, auf dem keine Visual C++-Bibliotheken vorhanden sind.  
  
### <a name="to-deploy-an-application-by-using-a-setup-project"></a>So stellen Sie eine Anwendung mithilfe eines Setup-Projekts bereit  
  
1.  Verwenden Sie den **MFC-Anwendungs-Assistenten** zum Erstellen einer neuen Visual Studio-Projektmappe. Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Visual C++**, klicken Sie auf **MFC** und dann auf **MFC-Anwendung**, geben Sie dann einen Namen für das Projekt ein, und klicken Sie auf **OK**, um den Assistenten zu finden.  
  
2.  Ändern Sie die aktive Projektmappenkonfiguration in **Release**. Klicken Sie im Menü **Build** auf **Konfigurations-Manager**. Wählen Sie im Dialogfeld **Konfigurations-Manager** im Dropdownfeld **Aktive Projektmappenkonfiguration** die Option **Release** aus.  
  
3.  Drücken Sie F7, um die Anwendung zu erstellen. Oder klicken Sie im Menü **Build** auf **Projektmappe erstellen**. Dadurch wird dem Setup-Projekt ermöglicht, die Ausgabe dieses MFC-Anwendungsprojekts zu verwenden.  
  
4.  Laden Sie InstallShield Limited Edition (ISLE) herunter, falls Sie das noch nicht getan haben. Visual Studio-Entwickler erhalten es kostenlos, und es ersetzt die Funktionen der Visual Studio-Projektvorlagen für Setup und Bereitstellung. Wenn eine Verbindung zum Internet besteht, öffnen Sie das Dialogfeld **Neues Projekt**, indem Sie in der Menüleiste auf **Datei**, **Neu** und **Projekt** klicken oder im **Projektmappen-Explorer** mit der rechten Maustaste auf Ihre Projektmappe klicken und dann auf **Hinzufügen**, **Neues Projekt** klicken. Erweitern Sie den Knoten **Andere Projekttypen**, wählen Sie dann **InstallShield Limited Edition aktivieren** im Knoten **Setup und Bereitstellung** aus, und führen Sie die angezeigten Anweisungen aus. Nachdem Sie ISLE heruntergeladen, installiert und aktiviert haben, schließen Sie Visual Studio und öffnen Sie das Programm erneut.  
  
5.  Öffnen Sie erneut das Dialogfeld **Neues Projekt**, erweitern Sie den Knoten **Andere Projekttypen**, und wählen Sie **InstallShield Limited Edition-Projekt** im Knoten **InstallShield Limited Edition** aus.  
  
6.  Führen Sie die Anweisungen im Knoten **Erste Schritte** des Setup-Projekts aus, das von der InstallShield Limited Edition-Vorlage erstellt wurde, um Ihrem Visual Studio-MFC-Projekt einen Ausgabeverweis hinzuzufügen.  
  
7.  Erstellen Sie das Setup-Projekt, um die Installationsdatei zu erstellen („setup.exe“). Klicken Sie dazu im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten „Setup-Projekt“, und klicken Sie dann auf **Erstellen**.  
  
     InstallShield Limited Edition erstellt die Setupdatei in der Setup-Projektstruktur (standardmäßig befindet sich diese im Unterordner Express\SingleImage\DiskImages\DISK1 des Setup-Projekts).  
  
8.  Führen Sie das Setupprogramm auf einem zweiten Computer aus, der über keine der Visual C++-Bibliotheken verfügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)