---
title: Das Einrichten eines statischen Links zum Registrierungscode (nur C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a66ca33aa95ea6ffd59860cf0a55e51266ef5cb
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757697"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Das Einrichten eines statischen Links zum Registrierungscode (nur C++)

C++-Clients können mit eine statische Verknüpfung zum Code der Registrierung erstellen. Statische Verknüpfung von der Registrierungsstelle Parser wird ein Releasebuild ca. 5 KB hinzugefügt.

Die einfachste Möglichkeit zum Einrichten der statischen Verknüpfung wird angenommen, Sie haben angegeben [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) in der Deklaration des Objekts. (Dies ist der Standardspezifikation verwendet die ATL)

### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Zum Erstellen eines statischen Links mit Hilfe von DECLARE_REGISTRY_RESOURCEID

1. Geben Sie [/d](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` anstelle von/d **_ATL_DLL**.

2. Kompilieren Sie neu.

## <a name="see-also"></a>Siehe auch

[Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md)

