---
title: In einer MFC-Datenbankanwendung Menü Datei | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- File menu
- database applications [MFC], File menu commands
ms.assetid: 92dafb75-c1b3-4860-80a0-87a83bfc36f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71e669336e4a23f1a34e0bbd65bd8123e0df3335
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="file-menu-in-an-mfc-database-application"></a>Das Dateimenü in einer MFC-Datenbankanwendung
Wenn Sie eine MFC-datenbankanwendung erstellen und Sie keine Serialisierung verwenden, wie Sie interpretieren öffnen, schließen, speichern, und speichern sollten als Befehle, auf das Menü Datei dafür gibt es keine Richtlinien für diese Frage, hier sind einige Vorschläge:  
  
-   Eliminieren Sie öffnen Sie im Menü Datei-Befehl vollständig.  
  
-   Interpretieren Sie den Befehl "Datenbank öffnen" öffnen und Anzeigen des Benutzers eine Liste der Datenquellen, die von die Anwendung erkannt.  
  
-   Interpretieren Sie den Befehl Öffnen als, vielleicht "Profil zu öffnen." Behalten Sie öffnen, für das Öffnen einer serialisierten Datei jedoch zum Speichern eines serialisierten Dokuments mit "Benutzerprofil"-Informationen, z. B. die Einstellungen des Benutzers, einschließlich seiner verwenden Sie die Datei, oder ihre Anmelde-ID (optional außer das Kennwort) und die Daten Datenquelle er am vor kurzem gearbeitet.  
  
 MFC-Anwendung-Assistent unterstützt, erstellen eine Anwendung mit keine dokumentbezogenen dateimenübefehle. Wählen Sie die **-Datenbanksicht ohne Unterstützung der** option die **-Datenbanken unterstützen** Seite.  
  
 Um einen Menübefehl Datei auf besondere Weise interpretieren zu können, müssen Sie eine oder mehrere Befehlshandler überschreiben, meist in Ihrem `CWinApp`-Klasse. Wenn Sie vollständig überschreiben, z. B. `OnFileOpen` (implementiert der `ID_FILE_OPEN` Befehl) bedeutet "geöffnete Datenbank:"  
  
-   Rufen Sie nicht die Basisklassenversion von `OnFileOpen`, da Sie das Framework standardmäßige Implementierung des Befehls vollständig ersetzen möchten.  
  
-   Verwenden Sie stattdessen den Handler, um ein Dialogfeld, das Auflisten der Datenquellen anzuzeigen. Sie können ein derartiges Dialogfeld anzeigen, indem Aufrufen `CDatabase::OpenEx` oder `CDatabase::Open` mit dem Parameter **NULL**. Daraufhin wird ein ODBC-Dialogfeld, in dem alle verfügbaren Datenquellen auf dem Computer des Benutzers angezeigt.  
  
-   Da nicht-datenbankanwendungen in der Regel ein ganzes Dokument speichern, müssen wahrscheinlich Speichern entfernen möchten, und speichern Sie als Implementierungen, es sei denn, Sie ein serialisiertes Dokument verwenden, um Profilinformationen zu speichern. Andernfalls könnten Sie implementieren Befehl Speichern unter, beispielsweise "Transaktion ein Commit ausgeführt." Finden Sie unter [technischen Hinweis 22](../mfc/tn022-standard-commands-implementation.md) für Weitere Informationen zu diesen Befehlen zu überschreiben.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung: Serialisierung im Vergleich zur Datenbank-e/a](../mfc/serialization-serialization-vs-database-input-output.md)

