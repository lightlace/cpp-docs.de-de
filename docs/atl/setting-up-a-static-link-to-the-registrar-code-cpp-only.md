---
title: Einrichten einer statischen Verknüpfung an den Code Registrierungsstelle (nur C++) | Microsoft Docs
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
ms.openlocfilehash: dca93c8f0fcae578700a9d9970977179fbd142d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360187"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Einrichten einer statischen Verknüpfung an den Code Registrierungsstelle (nur C++)
C++-Clients können eine statische Verknüpfung für die Registrierungsstelle Code erstellen. Statisches verknüpfen die Registrierungsstelle Parser wird ein Releasebuild dahingehend ca. 5 KB hinzugefügt.  
  
 Die einfachste Möglichkeit zum Einrichten der statischen Verknüpfung wird angenommen, Sie haben angegeben [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) in der Deklaration des Objekts. (Dies ist der Standardspezifikation, die durch die ATL verwendet)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Zum Erstellen eines statischen Links mit DECLARE_REGISTRY_RESOURCEID  
  
1.  Geben Sie [/d](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` anstelle von/d **_ATL_DLL**.  
  
2.  Kompilieren Sie erneut.  
  
## <a name="see-also"></a>Siehe auch  
 [Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md)

