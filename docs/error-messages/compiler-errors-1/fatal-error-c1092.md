---
title: Schwerwiegender Fehler C1092 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9852b7b3d695d5414e52727ce672ee3258f6840b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077151"
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