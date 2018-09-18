---
title: Projektbuildfehler PRJ0019 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0019
dev_langs:
- C++
helpviewer_keywords:
- PRJ0019
ms.assetid: 5390a62b-aacf-4bc8-b9d7-08f1e0233423
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06ea422a272b43f7e6226b330a210c0c6ea3f977
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038086"
---
# <a name="project-build-error-prj0019"></a>Projektbuildfehler PRJ0019

Ein Tool hat einen Fehlercode von zurückgegeben.

Eine Fehlerstufe erreicht, die für einen benutzerdefinierten Buildschritt oder Buildereignis ungleich NULL war.

Sie werden PRJ0019, wenn ein Tool einen Fehlercode aber keine Fehlermeldung zurückgegeben. Dies kann beispielsweise vorkommen, wenn Sie die Ausgabe von MIDL an NUL umleiten.

Finden Sie unter [Problembehandlung benutzerdefinierter Buildschritte und Buildereignisse](../../ide/troubleshooting-build-customizations.md) für Weitere Informationen.

Dieser Fehler kann auch auftreten, wenn Sie als Mitglied der Gruppe der Benutzer ausgeführt werden, und administrativer Zugriff erforderlich ist. Weitere Informationen finden Sie unter [Ausführen als Mitglied der Gruppe Benutzer](../../security/running-as-a-member-of-the-users-group.md).