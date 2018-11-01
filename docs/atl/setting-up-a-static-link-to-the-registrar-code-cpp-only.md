---
title: Das Einrichten eines statischen Links zum Registrierungscode (nur C++)
ms.date: 11/04/2016
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
ms.openlocfilehash: e5f09ce4626e030c43ecc30ca44d1ac738341c6c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557408"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Das Einrichten eines statischen Links zum Registrierungscode (nur C++)

C++-Clients können mit eine statische Verknüpfung zum Code der Registrierung erstellen. Statische Verknüpfung von der Registrierungsstelle Parser wird ein Releasebuild ca. 5 KB hinzugefügt.

Die einfachste Möglichkeit zum Einrichten der statischen Verknüpfung wird angenommen, Sie haben angegeben [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) in der Deklaration des Objekts. (Dies ist der Standardspezifikation verwendet die ATL)

## <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Zum Erstellen eines statischen Links mit Hilfe von DECLARE_REGISTRY_RESOURCEID

1. Geben Sie [/d](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` anstelle von/d **_ATL_DLL**.

1. Kompilieren Sie neu.

## <a name="see-also"></a>Siehe auch

[Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md)
