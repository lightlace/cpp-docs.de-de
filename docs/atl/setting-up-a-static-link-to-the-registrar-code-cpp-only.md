---
title: Das Einrichten eines statischen Links zum Registrierungscode (nur C++)
ms.date: 11/04/2016
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
ms.openlocfilehash: b95bd17abca3237710956f3a1bf1b1d6fa9df51e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265326"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Das Einrichten eines statischen Links zum Registrierungscode (nur C++)

C++-Clients können mit eine statische Verknüpfung zum Code der Registrierung erstellen. Statische Verknüpfung von der Registrierungsstelle Parser wird ein Releasebuild ca. 5 KB hinzugefügt.

Die einfachste Möglichkeit zum Einrichten der statischen Verknüpfung wird angenommen, Sie haben angegeben [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) in der Deklaration des Objekts. (Dies ist der Standardspezifikation verwendet die ATL)

## <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Zum Erstellen eines statischen Links mit Hilfe von DECLARE_REGISTRY_RESOURCEID

1. Geben Sie [/d](../build/reference/d-preprocessor-definitions.md)  **\_ATL\_statische\_Registrierung** anstelle von **/d \_ATL\_DLL**.

1. Kompilieren Sie neu.

## <a name="see-also"></a>Siehe auch

[Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md)
