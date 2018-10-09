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
ms.openlocfilehash: 3bde1d369ce5339f07ea36979ef50ddccb0d30d1
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860276"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Das Einrichten eines statischen Links zum Registrierungscode (nur C++)

C++-Clients können mit eine statische Verknüpfung zum Code der Registrierung erstellen. Statische Verknüpfung von der Registrierungsstelle Parser wird ein Releasebuild ca. 5 KB hinzugefügt.

Die einfachste Möglichkeit zum Einrichten der statischen Verknüpfung wird angenommen, Sie haben angegeben [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) in der Deklaration des Objekts. (Dies ist der Standardspezifikation verwendet die ATL)

## <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Zum Erstellen eines statischen Links mit Hilfe von DECLARE_REGISTRY_RESOURCEID

1. Geben Sie [/d](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` anstelle von/d **_ATL_DLL**.

1. Kompilieren Sie neu.

## <a name="see-also"></a>Siehe auch

[Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md)
