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
ms.openlocfilehash: 734018229eff0db3a1ed1a779be39e59b75447f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="command-object-interfaces"></a>Befehlsobjekt-Schnittstellen
Das Befehlsobjekt verwendet die `IAccessor` Schnittstelle parameterbindungen angeben. Der Consumer ruft `IAccessor::CreateAccessor`, übergibt es ein Array von `DBBINDING` Strukturen. `DBBINDING`enthält Informationen über die spaltenbindungen (z. B. Typ und Länge). Der Anbieter empfängt die Strukturen und bestimmt, wie die Daten übertragen werden sollen, und gibt an, ob die Konvertierung erforderlich sind.  
  
 Die `ICommandText` Schnittstelle bietet eine Möglichkeit, einen Textbefehl anzugeben. Die `ICommandProperties` Schnittstelle behandelt alle Befehlseigenschaften.  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)