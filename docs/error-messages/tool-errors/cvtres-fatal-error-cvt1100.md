---
title: 'CVTRES: Schwerwiegender Fehler CVT1100'
ms.date: 11/04/2016
f1_keywords:
- CVT1100
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
ms.openlocfilehash: c7e65ccc79852ec99dd2406398fe1b3cdecacde7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406274"
---
# <a name="cvtres-fatal-error-cvt1100"></a>CVTRES: Schwerwiegender Fehler CVT1100

Doppelte Ressource: Typ: Typ, Name: Name, Sprache: Sprache, Flags: Flags, Größe: Größe

Die angegebene Ressource wurde mehrmals angegeben.

Sie erhalten diesen Fehler auf, bei der Linker eine Typbibliothek erstellt, und Sie haben keinen [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) und eine Ressource in Ihrem Projekt bereits 1 verwendet. In diesem Fall geben Sie/TLBID und eine andere Zahl bis 65535.