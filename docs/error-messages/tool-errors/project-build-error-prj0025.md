---
title: Projektbuildfehler PRJ0025
ms.date: 08/27/2018
f1_keywords:
- PRJ0025
helpviewer_keywords:
- PRJ0025
ms.assetid: 57725c78-bc63-44f3-9667-2969b2d7c41d
ms.openlocfilehash: 5f3699dce75a20b9cc6e1d712bc5702543ab7b6c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383946"
---
# <a name="project-build-error-prj0025"></a>Projektbuildfehler PRJ0025

> Batchdatei '*Datei*"enthält Unicodeinhalt, der nicht in ANSI-Codepage des Benutzers übersetzt werden konnte.
>
> *Unicode-Inhalt der Datei*

Das Projektsystem gefunden, Unicode-Inhalt in einer benutzerdefinierten Buildregel, oder erstellen, die ordnungsgemäß für aktuelle ANSI-Codepage des Benutzers übersetzt werden kann.

Die Auflösung für diesen Fehler ist, aktualisieren Sie den Inhalt der Buildregel oder Buildereignisses unter Verwendung von ANSI oder die Codepage auf dem Computer installieren und als dem als Standard festgelegt haben.

Für Weitere Informationen über benutzerdefinierte Buildschritte und Buildereignisse, finden Sie unter [benutzerdefinierte Buildschritte und Buildereignisse](../../build/understanding-custom-build-steps-and-build-events.md).