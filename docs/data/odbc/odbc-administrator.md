---
title: ODBC-Administrator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- installing ODBC
- ODBC data sources [C++], ODBC Administrator
- ODBC drivers [C++], installing
- ODBC [C++], ODBC Administrator
- Administrator in ODBC
- administration ODBC Administrator
- ODBC Administrator [C++]
- drivers [C++], ODBC
ms.assetid: b8652790-3437-4e7d-bc83-6ea6981f008b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 834825b38eb8d5c81752dfed85f44202fbce3299
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="odbc-administrator"></a>ODBC-Administrator
ODBC-Administrator registriert und konfiguriert die [Datenquellen](../../data/odbc/data-source-odbc.md) für Sie verfügbaren entweder lokal oder über ein Netzwerk. Die Assistenten erstellen mithilfe der vom ODBC-Administrator bereitgestellten Informationen Code in Anwendungen, der Verbindungen zu Datenquellen für den Benutzer aufbaut.  
  
 Zur Einrichtung einer ODBC-Datenquelle zur Verwendung mit MFC-ODBC-Datenbankklassen oder DAO-Klassen muss die Datenquelle zunächst registriert und konfiguriert werden. Zum Hinzufügen und Entfernen von Datenquellen verwenden Sie den ODBC-Administrator. Je nach ODBC-Treiber können Sie auch neue Datenquellen erstellen.  
  
 Der ODBC-Administrator wird beim Setup installiert. Wenn Sie ausgewählt haben **benutzerdefinierte** Installation, und wählen Sie keine ODBC-Treiber in den **Datenbankoptionen** (Dialogfeld), müssen Sie zum Ausführen von Setup erneut aus, um die erforderlichen Dateien zu installieren.  
  
 Wählen Sie beim Setup die ODBC-Treiber aus, die Sie installieren möchten. Später können Sie mit Setup für Visual C++ zusätzliche Treiber installieren, die in Visual C++ mitgeliefert werden.  
  
 Wenn Sie ODBC-Treiber installieren möchten, die nicht in Visual C++ mitgeliefert werden, müssen Sie das Setup ausführen, das mit dem Treiber geliefert wurde.  
  
#### <a name="to-install-odbc-drivers-that-ship-with-visual-c"></a>So installieren Sie ODBC-Treiber, die in Visual C++ mitgeliefert werden  
  
1.  Starten Sie von der Visual C++-CD das Programm Setup.  
  
     Das Begrüßungsdialogfeld von Setup wird angezeigt.  
  
2.  Klicken Sie auf **Weiter** in jedem Dialogfeld, bis Sie erreichen die **Installationsoptionen** (Dialogfeld). Wählen Sie **benutzerdefinierte**, und klicken Sie dann auf `Next`.  
  
3.  Deaktivieren Sie alle Kontrollkästchen in der **Setup für Microsoft Visual C++** (Dialogfeld), mit Ausnahme der **Datenbankoptionen** Kontrollkästchen, und klicken Sie dann auf **Details** zum Anzeigen der **Datenbankoptionen** (Dialogfeld).  
  
4.  Deaktivieren der **Microsoft Datenzugriffsobjekte** wählen Sie das Kontrollkästchen der **Microsoft ODBC-Treiber** Kontrollkästchen, und klicken Sie dann auf **Details**.  
  
     Die **Microsoft ODBC-Treiber** Dialogfeld wird angezeigt.  
  
5.  Wählen Sie die Treiber zu installieren, und klicken Sie dann auf **OK** zweimal.  
  
6.  Klicken Sie auf **Weiter** auf den folgenden Dialogfeldern, um die Installation zu beginnen. Setup benachrichtigt Sie, wenn die Installation beendet ist.  
  
 Wenn die Treiber installiert sind, können Sie mit dem ODBC-Administrator die Datenquelle konfigurieren. In der Systemsteuerung finden Sie das ODBC-Symbol.  
  
## <a name="see-also"></a>Siehe auch  
 [Open Sie Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md)