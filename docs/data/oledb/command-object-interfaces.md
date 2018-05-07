---
title: Objektschnittstelle Befehl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9c597cc30e23ffce2787eac6c13f6ba8c53f96c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="command-object-interfaces"></a>Befehlsobjekt-Schnittstellen
Das Befehlsobjekt verwendet die `IAccessor` Schnittstelle parameterbindungen angeben. Der Consumer ruft `IAccessor::CreateAccessor`, übergibt es ein Array von `DBBINDING` Strukturen. `DBBINDING` enthält Informationen über die spaltenbindungen (z. B. Typ und Länge). Der Anbieter empfängt die Strukturen und bestimmt, wie die Daten übertragen werden sollen, und gibt an, ob die Konvertierung erforderlich sind.  
  
 Die `ICommandText` Schnittstelle bietet eine Möglichkeit, einen Textbefehl anzugeben. Die `ICommandProperties` Schnittstelle behandelt alle Befehlseigenschaften.  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)