---
title: Projektbuildfehler PRJ0019
ms.date: 11/04/2016
f1_keywords:
- PRJ0019
helpviewer_keywords:
- PRJ0019
ms.assetid: 5390a62b-aacf-4bc8-b9d7-08f1e0233423
ms.openlocfilehash: e97d9488df0eeb666cb78354d0363c2a359a159d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359396"
---
# <a name="project-build-error-prj0019"></a>Projektbuildfehler PRJ0019

Ein Tool hat einen Fehlercode von zurückgegeben.

Eine Fehlerstufe erreicht, die für einen benutzerdefinierten Buildschritt oder Buildereignis ungleich NULL war.

Sie werden PRJ0019, wenn ein Tool einen Fehlercode aber keine Fehlermeldung zurückgegeben. Dies kann beispielsweise vorkommen, wenn Sie die Ausgabe von MIDL an NUL umleiten.

Finden Sie unter [Problembehandlung benutzerdefinierter Buildschritte und Buildereignisse](../../build/troubleshooting-build-customizations.md) für Weitere Informationen.

Dieser Fehler kann auch auftreten, wenn Sie als Mitglied der Gruppe der Benutzer ausgeführt werden, und administrativer Zugriff erforderlich ist. Weitere Informationen finden Sie unter [Ausführen als Mitglied der Gruppe Benutzer](../../security/running-as-a-member-of-the-users-group.md).