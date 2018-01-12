---
title: Objektschnittstelle Befehl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3d83f0a14562985386f0f1f75cfcd99518fea6f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="command-object-interfaces"></a>Befehlsobjekt-Schnittstellen
Das Befehlsobjekt verwendet die `IAccessor` Schnittstelle parameterbindungen angeben. Der Consumer ruft `IAccessor::CreateAccessor`, übergibt es ein Array von `DBBINDING` Strukturen. `DBBINDING`enthält Informationen über die spaltenbindungen (z. B. Typ und Länge). Der Anbieter empfängt die Strukturen und bestimmt, wie die Daten übertragen werden sollen, und gibt an, ob die Konvertierung erforderlich sind.  
  
 Die `ICommandText` Schnittstelle bietet eine Möglichkeit, einen Textbefehl anzugeben. Die `ICommandProperties` Schnittstelle behandelt alle Befehlseigenschaften.  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)