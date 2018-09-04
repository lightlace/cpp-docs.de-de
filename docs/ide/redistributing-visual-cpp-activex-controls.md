---
title: Verteilen von Visual C++ ActiveX-Steuerelementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d62669ffef0ae1e5788dcf4086a1c5b58e7728ff
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683351"
---
# <a name="redistributing-visual-c-activex-controls"></a>Neuverteilen von Visual C++ ActiveX-Steuerelementen
Visual C++ 6.0 stellt ActiveX-Steuerelemente bereit, die Sie in Anwendungen verwenden können, die Sie dann verteilen. Diese Steuerelemente sind nicht mehr in Visual C++ enthalten. Aufgrund der Lizenzvereinbarungen für Visual C++ 6.0 können Sie diese Steuerelemente mit Anwendungen verteilen, die in Visual C++ entwickelt wurden.  
  
> [!NOTE]
>  Visual C++ 6.0 wird jedoch nicht mehr von Microsoft unterstützt.  
  
 Eine Liste der verteilbaren Visual C++ 6.0 ActiveX-Steuerelemente finden Sie unter Common\Redist\Redist.txt auf Disk 1 der Visual C++ 6.0-Produkt-CD.  
  
 Wenn Sie Anwendungen verteilen, müssen Sie die OCX-Datei für das ActiveX-Steuerelement mithilfe von „Regsvr32.exe“ installieren und registrieren. Darüber hinaus sollten Sie sicherstellen, dass der Zielcomputer über die aktuellen Versionen der folgenden Systemdateien verfügt (die Sternchen geben Dateien an, die registriert werden müssen):  
  
-   Asycfilt.dll  
  
-   Comcat.dll \*  
  
-   Oleaut32.dll \*  
  
-   Olepro32.dll \*  
  
-   Stdole2.tlb  
  
 Wenn diese DLLs nicht auf dem Zielsystem verfügbar sind, müssen Sie sie mithilfe des vorgeschriebenen Mechanismus zum Aktualisieren des entsprechenden Betriebssystems aktualisieren. Sie können die neuesten Service Packs für Windows-Betriebssysteme unter [http://windowsupdate.microsoft.com](http://windowsupdate.microsoft.com) herunterladen.  
  
 Wenn Sie ein ActiveX-Steuerelement verwenden, das eine Verbindung zu einer Datenbank herstellt, müssen Sie auch den Namen der Datenquelle auf dem Zielcomputer replizieren. Diesen Vorgang können Sie mit Funktionen wie `ConfigDSN` programmgesteuert durchführen.  
  
 Einige verteilbare ActiveX-Steuerelemente verfügen über zusätzliche Abhängigkeiten. Für jede OCX-Datei im Ordner „Os\System“ auf der Visual C++ 6.0-Produkt-CD gibt es auch eine DEP-Datei. Sehen Sie sich für jede OCX-Datei, die Sie verteilen möchten, mindestens einen der Einträge zur Verwendung in den entsprechenden DEP-Dateien an. Wenn eine Datei aufgeführt wird, müssen Sie sicherstellen, dass die Datei sich auch auf dem Zielcomputer befindet. Alle DLLs, die eine OCX-Datei direkt unterstützen, müssen registriert werden. (Damit „Regsvr32.exe“ erfolgreich ausgeführt wird, muss der Zielcomputer zunächst alle DLLs enthalten, die das Steuerelement statisch lädt.) Wenn eine DLL als Abhängigkeit aufgeführt wird und über eine DEP-Datei im Ordner „Os\System“ auf der Visual C++ 6.0-CD verfügt, müssen Sie auch diese DEP-Datei auf Einträge zur Verwendung überprüfen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md)