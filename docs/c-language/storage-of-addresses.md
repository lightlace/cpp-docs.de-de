---
title: Speicherung von Adressen
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 47b09ab6cd0b2045206daaee4badad32858ff934
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148737"
---
# <a name="storage-of-addresses"></a>Speicherung von Adressen

Die Menge des erforderlichen Arbeitsspeichers für eine Adresse und die Bedeutung der Adresse hängen von der Implementierung des Compilers ab. Für Zeiger auf verschiedene Typen kann nicht garantiert werden, dass sie die gleiche Länge haben. Daher ist **sizeof(char \*)** nicht unbedingt gleich **sizeof(int \*)**.

**Microsoft-spezifisch**

Für den Microsoft C-Compiler ist **sizeof(char \*)** gleich **sizeof(int \*)**.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Zeigerdeklarationen](../c-language/pointer-declarations.md)
