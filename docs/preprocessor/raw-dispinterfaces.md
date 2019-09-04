---
title: raw_dispinterfaces-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: 73c58b72b27de8dcf96e8ab9464d0fb6bce12b66
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216227"
---
# <a name="raw_dispinterfaces-import-attribute"></a>raw_dispinterfaces-Attribut importieren

**C++Zugeschnitten**

Weist den Compiler an, Wrapper Funktionen auf niedriger Ebene für Dispinterface-Methoden zu generieren, und für `IDispatch::Invoke` Eigenschaften, die den HRESULT-Fehlercode aufzurufen und zurückgeben.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **raw_dispinterfaces**

## <a name="remarks"></a>Hinweise

Wenn dieses Attribut nicht angegeben wird, werden nur Wrapper auf hoher Ebene generiert, die bei C++ einem Fehler Ausnahmen auslösen.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
