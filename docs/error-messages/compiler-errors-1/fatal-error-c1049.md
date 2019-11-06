---
title: Schwerwiegender Fehler C1049
description: Beschreibt den schwerwiegenden Compilerfehler C1049, ein ungültiges numerisches Argument und erläutert, wie es aufgelöst werden kann.
ms.date: 11/04/2019
f1_keywords:
- C1049
helpviewer_keywords:
- C1049
ms.openlocfilehash: f2669eec4bafb24f26c405d4fa74a96fe5337d13
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73633303"
---
# <a name="fatal-error-c1049"></a>Schwerwiegender Fehler C1049

> Ungültiges numerisches Argument „*value*“.

Der CL. Der exe-Befehlszeilen Parser hat einen *Wert* gefunden, in dem ein numerisches Argument erwartet wurde.

Ein C1049-Fehler kann auftreten, wenn der Compiler kein numerisches Argument für eine dieser Compileroptionen finden kann:

[/constexpr: Tiefe](/cpp/build/reference/constexpr-control-constexpr-evaluation)\
[/constexpr: Rückverfolgung](/cpp/build/reference/constexpr-control-constexpr-evaluation)\
[/constexpr: Schritte](/cpp/build/reference/constexpr-control-constexpr-evaluation)

Befehlszeilen-Compileroptionen, die ein numerisches Argument erwarten, können auch `Command line error D8004`, `Command line error D8021`, `Command line warning D9002`, `Command line warning D9014`oder `Command line warning D9024`melden.

Um diesen Fehler zu beheben, überprüfen Sie die Befehlszeile auf falsch platzierte oder fehlende Argumente. Stellen Sie sicher, dass keine unerwarteten Leerzeichen zwischen Optionen und Argumenten vorhanden sind. Die letzte Befehlszeile kann von Makros, Umgebungsvariablen oder anderen buildsystemvorgängen generiert werden. Daher ist es wichtig, sich die tatsächliche Befehlszeile anzusehen, die an den Compiler übermittelt wurde.

- In Befehls Dateien oder Makefiles können Sie einen **Echo** -Befehl verwenden, um die tatsächliche Befehlszeile zu melden.

- Öffnen Sie in Visual Studio das Dialogfeld **Eigenschaften Seiten** des Projekts. Ändern Sie auf der Seite **Konfigurations Eigenschaften** > **CC++ /**  > **Allgemein** die Eigenschaft **Start Banner unterdrücken** auf **Nein**. Klicken Sie auf **OK**, um die Änderungen zu speichern. Das **Ausgabe** Fenster zeigt nun die Befehlszeile an, wenn Sie direkt nach der Copyright Linie erstellen.

Andere Buildsysteme verfügen möglicherweise über Protokolldateien oder ausführliche Optionen, um die tatsächlich verwendeten Befehle anzuzeigen. Weitere Informationen finden Sie in der Dokumentation des Buildsystems.
