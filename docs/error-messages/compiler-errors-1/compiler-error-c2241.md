---
title: Compilerfehler C2241 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2241
dev_langs:
- C++
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd97551e0feaecce776cc552353716c67822f273
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055896"
---
# <a name="compiler-error-c2241"></a>Compilerfehler C2241

'Bezeichner': Memberzugriff ist eingeschränkt.

Der Code versucht, auf einen privaten oder geschützten Member zuzugreifen.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Ändern Sie die Zugriffsebene des Members.

1. Deklarieren Sie den Member als `friend` der zugreifenden Funktion.