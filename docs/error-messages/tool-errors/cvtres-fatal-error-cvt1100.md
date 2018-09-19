---
title: 'CVTRES: Schwerwiegender Fehler CVT1100 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CVT1100
dev_langs:
- C++
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18a5508301c54637fb34a751c8f1c4e307e47d50
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068961"
---
# <a name="cvtres-fatal-error-cvt1100"></a>CVTRES: Schwerwiegender Fehler CVT1100

Doppelte Ressource: Typ: Typ, Name: Name, Sprache: Sprache, Flags: Flags, Größe: Größe

Die angegebene Ressource wurde mehrmals angegeben.

Sie erhalten diesen Fehler auf, bei der Linker eine Typbibliothek erstellt, und Sie haben keinen [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) und eine Ressource in Ihrem Projekt bereits 1 verwendet. In diesem Fall geben Sie/TLBID und eine andere Zahl bis 65535.