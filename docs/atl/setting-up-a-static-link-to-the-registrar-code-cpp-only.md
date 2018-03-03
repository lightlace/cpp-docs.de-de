---
title: "Einrichten einer statischen Verknüpfung an den Code Registrierungsstelle (nur C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d49ed2a56738ec784c8a1a2cc3c13239f7317270
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Einrichten einer statischen Verknüpfung an den Code Registrierungsstelle (nur C++)
C++-Clients können eine statische Verknüpfung für die Registrierungsstelle Code erstellen. Statisches verknüpfen die Registrierungsstelle Parser wird ein Releasebuild dahingehend ca. 5 KB hinzugefügt.  
  
 Die einfachste Möglichkeit zum Einrichten der statischen Verknüpfung wird angenommen, Sie haben angegeben [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) in der Deklaration des Objekts. (Dies ist der Standardspezifikation, die durch die ATL verwendet)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>Zum Erstellen eines statischen Links mit DECLARE_REGISTRY_RESOURCEID  
  
1.  Geben Sie [/d](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` anstelle von/d**_ATL_DLL**.  
  
2.  Kompilieren Sie erneut.  
  
## <a name="see-also"></a>Siehe auch  
 [Registrierungskomponente (Registrar)](../atl/atl-registry-component-registrar.md)

