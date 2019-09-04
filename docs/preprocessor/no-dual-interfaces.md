---
title: no_dual_interfaces-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: 6270888f0d31e4fbe18fb3364995be8c73426b83
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220763"
---
# <a name="no_dual_interfaces-import-attribute"></a>no_dual_interfaces-Attribut importieren

**C++Zugeschnitten**

Ändert die Art, mit der der Compiler Wrapperfunktionen für Methoden der dualen Schnittstelle generiert.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **no_dual_interfaces**

## <a name="remarks"></a>Hinweise

Normalerweise ruft der Wrapper die-Methode über die virtuelle Funktions Tabelle für die-Schnittstelle auf. Mit **no_dual_interfaces**ruft `IDispatch::Invoke` der Wrapper stattdessen auf, um die Methode aufzurufen.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
