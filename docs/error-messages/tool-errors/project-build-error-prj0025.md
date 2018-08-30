---
title: Projektbuildfehler prj0025 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0025
dev_langs:
- C++
helpviewer_keywords:
- PRJ0025
ms.assetid: 57725c78-bc63-44f3-9667-2969b2d7c41d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 949e36424fc213459e56332c0802d2719581bac1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209811"
---
# <a name="project-build-error-prj0025"></a>Projektbuildfehler PRJ0025

> Batchdatei '*Datei*"enthält Unicodeinhalt, der nicht in ANSI-Codepage des Benutzers übersetzt werden konnte.
>
> *Unicode-Inhalt der Datei*

Das Projektsystem gefunden, Unicode-Inhalt in einer benutzerdefinierten Buildregel, oder erstellen, die ordnungsgemäß für aktuelle ANSI-Codepage des Benutzers übersetzt werden kann.

Die Auflösung für diesen Fehler ist, aktualisieren Sie den Inhalt der Buildregel oder Buildereignisses unter Verwendung von ANSI oder die Codepage auf dem Computer installieren und als dem als Standard festgelegt haben.

Für Weitere Informationen über benutzerdefinierte Buildschritte und Buildereignisse, finden Sie unter [benutzerdefinierte Buildschritte und Buildereignisse](../../ide/understanding-custom-build-steps-and-build-events.md).