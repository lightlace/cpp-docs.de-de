---
title: Speicherung von Adressen
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 2a0e218d4d34fa1482986ecccd7da8adba38086b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539372"
---
# <a name="storage-of-addresses"></a>Speicherung von Adressen

Die Menge des erforderlichen Arbeitsspeichers für eine Adresse und die Bedeutung der Adresse hängen von der Implementierung des Compilers ab. Für Zeiger auf verschiedene Typen kann nicht garantiert werden, dass sie die gleiche Länge haben. Daher ist **sizeof(char \*)** nicht unbedingt gleich **sizeof(int \*)**.

**Microsoft-spezifisch**

Für den Microsoft C-Compiler ist **sizeof(char \*)** gleich **sizeof(int \*)**.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Zeigerdeklarationen](../c-language/pointer-declarations.md)