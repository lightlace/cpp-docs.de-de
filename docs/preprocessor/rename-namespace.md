---
title: rename_namespace-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: d319d7390e7c7dce070a35be44aad37c7a34e1a0
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216654"
---
# <a name="rename_namespace-import-attribute"></a>rename_namespace-Attribut importieren

**C++Zugeschnitten**

Benennt den Namespace, der die Inhalte der Typbibliothek enthält, um.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **rename_namespace (** "*NewName*" **)**

### <a name="parameters"></a>Parameter

*NewName*\
Der neue Name des neuen Namespace.

## <a name="remarks"></a>Hinweise

Das **rename_namespace** -Attribut übernimmt das einzige Argument *NewName*, das den neuen Namen für den Namespace angibt.

Um den Namespace zu entfernen, verwenden Sie stattdessen das [no_namespace](../preprocessor/no-namespace.md) -Attribut.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
