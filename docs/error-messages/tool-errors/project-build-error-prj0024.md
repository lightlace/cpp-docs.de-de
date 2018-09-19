---
title: Projektbuildfehler prj0024 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0024
dev_langs:
- C++
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb539a5f1ee5f1aa5f9d828d93fa6d0dc8690c22
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215597"
---
# <a name="project-build-error-prj0024"></a>Projektbuildfehler PRJ0024

> Unicodepfad '*Pfad*' konnte nicht in ANSI-Codepage des Benutzers übersetzt werden.

*Pfad* ist die ursprüngliche Unicode-Version von der Path-Zeichenfolge. Dieser Fehler kann in Fällen auftreten, wenn ein Unicodepfad, der für die aktuelle Codepage des Systems nicht direkt in ANSI übersetzt werden kann nicht vorhanden ist.

Dieser Fehler kann auftreten, wenn Sie arbeiten mit einem Projekt, das entwickelt wurde auf einem System, das Verwenden einer Codepage, die nicht auf Ihrem Computer vorhanden ist.

Die Auflösung für diesen Fehler ist, aktualisieren Sie den Pfad zur Verwendung von ANSI-Text oder um die Codepage auf dem Computer installieren und als dem als Standard festgelegt haben.