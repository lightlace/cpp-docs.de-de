---
title: Projektbuildwarnung PRJ0042 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0042
dev_langs:
- C++
helpviewer_keywords:
- PRJ0042
ms.assetid: 682c9999-6f85-409f-b102-00c93243f74f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 260da8ac336c640ea875610b2c62e6c42c7d335e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211349"
---
# <a name="project-build-warning-prj0042"></a>Projektbuildwarnung PRJ0042

> Die 'Outputs-Eigenschaft für den benutzerdefinierten Buildschritt für die Datei"*Datei*' ist nicht festgelegt. Der benutzerdefinierte Buildschritt wird übersprungen.

Ein benutzerdefinierter Buildschritt wurde nicht ausgeführt werden, da keine Ausgabe angegeben wurde.

Um diesen Fehler zu beheben, führen Sie eine der folgenden:

- Schließen Sie den benutzerdefinierten Buildschritt aus dem Build.

- Fügen Sie eine Ausgabe hinzu.

- Löschen Sie den Inhalt des Befehls für den benutzerdefinierten Buildschritt an.