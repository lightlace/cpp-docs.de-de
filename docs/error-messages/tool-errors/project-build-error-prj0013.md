---
title: Projektbuildfehler prj0013 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0013
dev_langs:
- C++
helpviewer_keywords:
- PRJ0013
ms.assetid: 95e7bafd-63c8-4b2d-b778-f19cdf9ba36c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7a151ca34d680a517c405e5cb6f91c18d35bedd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102644"
---
# <a name="project-build-error-prj0013"></a>Projektbuildfehler PRJ0013

Möglicherweise sind nicht genügend Systemressourcen vorhanden. Ein Pipe, der zum Starten eines Builds erforderlich ist, konnte nicht erstellt werden.

Dieser Fehler weist darauf hin, dass möglicherweise nicht genügend Systemressourcen vorhanden sind. Sie können diesen Fehler beheben, indem Sie die Systemressourcenauslastung durch andere Prozesse/Anwendungen verringern.

Dieser Fehler kann auch auftreten, wenn Ihre Sicherheitsstufe nicht zum Erstellen von Pipes ausreicht (siehe [CreatePipe](https://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)).