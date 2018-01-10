---
title: Neuverteilen von Visual C++ ActiveX-Steuerelementen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c520d365a259c36baab8edeb9049aab9ac89925a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-visual-c-activex-controls"></a>Neuverteilen von Visual C++ ActiveX-Steuerelementen
Visual C++ 6.0 liefert ActiveX-Steuerelemente, die Sie in Anwendungen verwenden können, die Sie dann erneut verteilen. Diese Steuerelemente sind nicht mehr in Visual C++ enthalten. Pro die Lizenzverträge für Visual C++ 6.0 können Sie diese Steuerelemente mit Anwendungen, die in Visual C++ entwickelt verteilt.  
  
> [!NOTE]
>  Visual C++ 6.0 wird nicht mehr von Microsoft unterstützt.  
  
 Eine Liste der verteilbaren Visual C++ 6.0-ActiveX-Steuerelemente finden Sie unter Common\Redist\Redist.txt auf CD 1 der Visual C++ 6.0-Produkt-CD.  
  
 Bei der Verteilung von Anwendungen, müssen Sie installieren und registrieren die ".ocx" für das ActiveX-Steuerelement (mit Regsvr32.exe). Darüber hinaus sollten Sie sicherstellen, dass der Zielcomputer die aktuelle Versionen der folgenden Systemdateien hat (ein Sternchen gibt an, dass die Datei muss registriert werden):  
  
-   "Asycfilt.dll"  
  
-   Comcat.dll *  
  
-   Oleaut32.dll *  
  
-   "OLEPRO32.dll" *  
  
-   Stdole2.tlb  
  
 Wenn diese DLLs nicht auf dem Zielsystem verfügbar sind, müssen Sie diese mithilfe des vorgeschriebenen Mechanismus für das entsprechende Betriebssystem aktualisieren aktualisiert werden. Sie können die neuesten Servicepacks für Windows-Betriebssysteme aus herunterladen [http://windowsupdate.microsoft.com](http://windowsupdate.microsoft.com).  
  
 Wenn Ihre Anwendung einen ActiveX-Steuerelemente, die einer Datenbank herstellt verwendet, müssen Sie die auf dem Zielsystem installiert Microsoft Data Access Components (MDAC) verfügen. Weitere Informationen finden Sie unter [Neuverteilen von Datenbankunterstützungsdateien](../ide/redistributing-database-support-files.md).  
  
 Wenn Sie ein ActiveX-Steuerelement verwenden, die einer Datenbank herstellt, müssen Sie auch den Datenquellennamen auf dem Zielcomputer replizieren. Hierzu können Sie programmgesteuert mit Funktionen wie z. B. `ConfigDSN`.  
  
 Einige verteilbare ActiveX-Steuerelemente sind zusätzliche abhängig. Für jede OCX-Datei im Ordner "Os\System" auf der Visual C++ 6.0-Produkt-CD gibt es auch eine DEP-Datei. Jede ".ocx"-Datei, die Sie verteilen möchten, finden Sie eine oder mehrere verwendet Einträge in der entsprechenden DEP-Datei. Wenn eine Datei aufgeführt ist, müssen Sie sicherstellen, dass die Datei auf dem Zielcomputer installiert ist. Alle DLLs, die direkte Unterstützung OCX-Datei müssen registriert werden. (Für Regsvr32.exe erfolgreich ausgeführt werden kann, muss der Zielcomputer zunächst alle DLLs, die das Steuerelement statisch lädt enthalten.) Darüber hinaus verfügt eine DLL, die als Abhängigkeit aufgeführt ist auch eine DEP-Datei im Ordner "Os\System" auf der Visual C++ 6.0-CD, müssen Sie auch diese Datei DEP verwendet Einträge überprüfen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md)