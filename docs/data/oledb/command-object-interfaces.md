---
title: Befehls-Schnittstellen | Microsoft-Dokumentation
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
ms.openlocfilehash: 8176bad2921edd22edaab1688e38bc7de275b0bb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074799"
---
# <a name="command-object-interfaces"></a>Befehlsobjekt-Schnittstellen

Das Befehlsobjekt verwendet die `IAccessor` Schnittstelle parameterbindungen angeben. Der Consumer ruft `IAccessor::CreateAccessor`, übergibt ein Array von `DBBINDING` Strukturen. `DBBINDING` enthält Informationen über die spaltenbindungen (z. B. Typ und Länge). Der Anbieter empfängt die Strukturen und bestimmt, wie die Daten übertragen werden sollen, und gibt an, ob Konvertierungen erforderlich sind.

Die `ICommandText` Schnittstelle bietet eine Möglichkeit, einen Text-Befehl anzugeben. Die `ICommandProperties` Schnittstelle verarbeitet alle Befehlseigenschaften.

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)