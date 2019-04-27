---
title: Schwerwiegender Fehler C1092
ms.date: 11/04/2016
f1_keywords:
- C1092
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
ms.openlocfilehash: 3268e5b124be40313bdc97b4c95d935ddd4f9160
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208543"
---
# <a name="fatal-error-c1092"></a>Schwerwiegender Fehler C1092

Bearbeiten und Fortfahren unterstützt keine Änderungen an Datentypen. Build erforderlich

Geändert oder einen Datentyp seit dem letzten erfolgreichen Build hinzugefügt wurden.

- Bearbeiten und Fortfahren unterstützt keine Änderungen an vorhandenen Datentypen, einschließlich Definitionen-Klasse, Struktur oder Enumeration. Sie müssen den Debugvorgang unterbrechen und erstellen Sie die Anwendung.

- Bearbeiten und Fortfahren unterstützt nicht das Hinzufügen von neuen Datentypen, wenn eine Datenbank-Programmdatei, z. B. vc*x*0 PDB-Datei (, in denen *x* ist die Hauptversion von Visual C++ verwendet) ist schreibgeschützt. Um Datentypen hinzuzufügen, muss der Compiler die PDB-Datei im Schreibmodus öffnen.

### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Um diesen Fehler zu entfernen, ohne die aktuelle Debugsitzung beenden

1. Ändern Sie den Datentyp wieder in den Zustand, den er vor dem Fehler hatte.

1. Wählen Sie im Menü **Debuggen** den Befehl **Codeänderungen übernehmen**aus.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>So entfernen Sie diesen Fehler, ohne den Quellcode zu ändern

1. Wählen Sie im Menü **Debuggen** die Option **Debuggen beenden**.

1. Wählen Sie im Menü **Erstellen** den Befehl **Erstellen**aus.

Weitere Informationen hierzu finden Sie unter [Unterstützte Codeänderungen](/visualstudio/debugger/supported-code-changes-cpp).