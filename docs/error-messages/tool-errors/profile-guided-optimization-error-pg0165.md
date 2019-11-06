---
title: Fehler bei der Profil gesteuerten Optimierung PG0165
description: Beschreibt PG0165-Fehler beim Lesen von PGO-Daten (Profil gesteuerte Optimierung).
ms.date: 10/30/2019
f1_keywords:
- PG0165
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
ms.openlocfilehash: c5e5c5d37f8c70a6c2a3d9f7a43c13bb46d0e25a
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626800"
---
# <a name="profile-guided-optimization-error-pg0165"></a>Fehler bei der Profil gesteuerten Optimierung PG0165

Beim Lesen Profil gesteuerter Optimierungs Daten ist ein Fehler aufgetreten. Dieser Fehler kann in verschiedenen Formen auftreten:

> "*Filename. PGD*" wird gelesen: "PGD-Version wird nicht unterstützt (Versions Konflikt)".

PGD-Dateien sind spezifisch für ein bestimmtes Compilertoolset. Dieser Fehler wird generiert, wenn Sie einen anderen Compiler als den verwenden, der zum Erstellen von *Dateiname. PGD*verwendet wurde. Der Fehler gibt an, dass dieses Compilertoolset die Daten aus *filename. PGD* nicht verwenden kann, um das aktuelle Programm zu optimieren. Um dieses Problem zu beheben, generieren Sie *filename*. PGD mit dem aktuellen Compilertoolset erneut.

> "*Filename. PGD*" wird gelesen: die PGD-Datei ist schreibgeschützt.

Dieser Fehler wird angezeigt, wenn die PGD-Datei im Dateisystem als schreibgeschützt gekennzeichnet ist. Um dieses Problem zu beheben, ändern Sie die Dateiattribute in Lese-/Schreibzugriff.
