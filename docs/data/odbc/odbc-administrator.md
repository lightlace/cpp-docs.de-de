---
title: ODBC-Administrator
ms.date: 11/04/2016
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
ms.openlocfilehash: ac893981ff8c697dc090f1e6ad5ac61886a69f99
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395845"
---
# <a name="odbc-administrator"></a>ODBC-Administrator

ODBC-Administrator registriert und konfiguriert die [Datenquellen](../../data/odbc/data-source-odbc.md) für Sie verfügbaren entweder lokal oder in einem Netzwerk. Die Assistenten erstellen mithilfe der vom ODBC-Administrator bereitgestellten Informationen Code in Anwendungen, der Verbindungen zu Datenquellen für den Benutzer aufbaut.

Zur Einrichtung einer ODBC-Datenquelle zur Verwendung mit MFC-ODBC-Datenbankklassen oder DAO-Klassen muss die Datenquelle zunächst registriert und konfiguriert werden. Zum Hinzufügen und Entfernen von Datenquellen verwenden Sie den ODBC-Administrator. Je nach ODBC-Treiber können Sie auch neue Datenquellen erstellen.

Der ODBC-Administrator wird beim Setup installiert. Wenn Sie ausgewählt haben **benutzerdefinierte** Installation, und wählen Sie keine ODBC-Treiber in der **Datenbankoptionen** (Dialogfeld), müssen Sie Setup erneut aus, um die notwendigen Dateien ausführen.

Wählen Sie beim Setup die ODBC-Treiber aus, die Sie installieren möchten. Später können Sie mit Setup für Visual C++ zusätzliche Treiber installieren, die in Visual C++ mitgeliefert werden.

Wenn Sie ODBC-Treiber installieren möchten, die nicht in Visual C++ mitgeliefert werden, müssen Sie das Setup ausführen, das mit dem Treiber geliefert wurde.

#### <a name="to-install-odbc-drivers-that-ship-with-visual-c"></a>So installieren Sie ODBC-Treiber, die in Visual C++ mitgeliefert werden

1. Starten Sie von der Visual C++-CD das Programm Setup.

   Das Begrüßungsdialogfeld von Setup wird angezeigt.

1. Klicken Sie auf **Weiter** in jedem Dialogfeld bis zu der **Installationsoptionen** Dialogfeld. Wählen Sie **benutzerdefinierte**, und klicken Sie dann auf **Weiter**.

1. Deaktivieren Sie alle Kontrollkästchen in der **Setup für Microsoft Visual C++** im Dialogfeld, mit Ausnahme der **Datenbankoptionen** , und klicken Sie dann auf **Details** zum Anzeigen der **Datenbankoptionen** Dialogfeld.

1. Deaktivieren der **Microsoft Data Access Objects** aktivieren Sie die Kontrollkästchen der **Microsoft ODBC-Treiber** , und klicken Sie dann auf **Details**.

   Die **Microsoft ODBC-Treiber** Dialogfeld wird angezeigt.

1. Wählen Sie die Treiber, die Sie installieren möchten, und klicken Sie dann auf **OK** zweimal.

1. Klicken Sie auf **Weiter** in den verbleibenden Dialogfeldern, um die Installation zu beginnen. Setup benachrichtigt Sie, wenn die Installation beendet ist.

Wenn die Treiber installiert sind, können Sie mit dem ODBC-Administrator die Datenquelle konfigurieren. In der Systemsteuerung finden Sie das ODBC-Symbol.

## <a name="see-also"></a>Siehe auch

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md)