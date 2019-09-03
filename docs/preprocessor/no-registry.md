---
title: no_registry-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: 7c81cc2f570cb9ac4e977dac6d55cb69e491d3b2
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220727"
---
# <a name="no_registry-import-attribute"></a>no_registry-Attribut importieren

**no_registry** weist den Compiler an, die Registrierung nicht nach Typbibliotheken zu durch `#import`suchen, die mit importiert wurden.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **no_registry**

### <a name="parameters"></a>Parameter

*Typbibliothek*\
Eine Typbibliothek.

## <a name="remarks"></a>Hinweise

Wenn eine Typbibliothek, auf die verwiesen wird, in den Includeverzeichnissen nicht gefunden wird, schlägt die Kompilierung fehl, auch wenn sich die Typbibliothek in der Registrierung  **no_registry** wird an andere Typbibliotheken weitergegeben, die `auto_search`implizit mit importiert werden.

Der Compiler durchsucht die Registrierung nie nach Typbibliotheken, die durch den Dateinamen angegeben und direkt `#import`an die übermittelt werden.

Wenn `auto_search` angegeben wird, werden die `#import` zusätzlichen-Direktiven mithilfe der **no_registry** -Einstellung des ursprünglichen `#import`generiert. Wenn die ursprüngliche `#import` Direktive **no_registry**war, `auto_search`ist ein `#import` -generiertes auch **no_registry**.

**no_registry** ist nützlich, wenn Sie Kreuz referenzierte Typbibliotheken importieren möchten. Dadurch wird verhindert, dass der Compiler eine ältere Version der Datei in der Registrierung findet. **no_registry** ist auch nützlich, wenn die Typbibliothek nicht registriert ist.

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
