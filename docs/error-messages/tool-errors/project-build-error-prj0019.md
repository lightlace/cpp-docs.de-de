---
title: Projektbuildfehler PRJ0019
ms.date: 11/04/2016
f1_keywords:
- PRJ0019
helpviewer_keywords:
- PRJ0019
ms.assetid: 5390a62b-aacf-4bc8-b9d7-08f1e0233423
ms.openlocfilehash: e97d9488df0eeb666cb78354d0363c2a359a159d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808091"
---
# <a name="project-build-error-prj0019"></a>Projektbuildfehler PRJ0019

Ein Tool hat einen Fehlercode von zurückgegeben.

Eine Fehlerstufe erreicht, die für einen benutzerdefinierten Buildschritt oder Buildereignis ungleich NULL war.

Sie werden PRJ0019, wenn ein Tool einen Fehlercode aber keine Fehlermeldung zurückgegeben. Dies kann beispielsweise vorkommen, wenn Sie die Ausgabe von MIDL an NUL umleiten.

Finden Sie unter [Problembehandlung benutzerdefinierter Buildschritte und Buildereignisse](../../build/troubleshooting-build-customizations.md) für Weitere Informationen.

Dieser Fehler kann auch auftreten, wenn Sie als Mitglied der Gruppe der Benutzer ausgeführt werden, und administrativer Zugriff erforderlich ist. Weitere Informationen finden Sie unter [Ausführen als Mitglied der Gruppe Benutzer](../../security/running-as-a-member-of-the-users-group.md).