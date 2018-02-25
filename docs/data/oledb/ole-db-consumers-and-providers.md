---
title: OLE DB-Consumer und-Anbieter | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ec0a8764ef8f5e906ad399d76a5a004c313f500b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB-Consumer und -Anbieter
Die OLE DB-Architektur verwendet das Modell der Consumer und-Anbieter. Ein Consumer fordert Daten. Ein Anbieter reagiert auf diese Anforderungen durch Anordnen von Daten in einem tabellarischen Format, und sie an den Consumer zurückgegeben wird. Jeder Aufruf, die der Consumer vornehmen können, muss im Anbieter implementiert werden.  
  
 Technisch definiert ist, ist ein Consumer ein System- oder Code (nicht unbedingt ein OLE DB-Komponente), die über OLE DB-Schnittstellen auf Daten zugreift. Die Schnittstellen werden in einem Anbieter implementiert. Daher ist ein Anbieter eine Softwarekomponente, die implementiert die OLE DB-Schnittstellen zum Zugriff auf Daten zu kapseln und auf andere Objekte (d. h. Verbraucher) verfügbar gemacht.  
  
 Im Hinblick auf Rollen Ruft ein Consumer Methoden auf OLE DB-Schnittstellen. OLE DB-Anbieter implementiert die erforderlichen OLE DB-Schnittstellen.  
  
 OLE DB-vermeidet die Begriffe Client und Server, da diese Rollen nicht immer, insbesondere in einer n-Tier-Situation bedeutungsvoll sind. Da ein Consumer einer Komponente auf einer Ebene werden konnte, die eine andere Komponente dient zum Aufrufen von eines Clients wäre Komponente verwirrend. Darüber hinaus verhält sich ein Anbieter manchmal eher wie einem Datenbanktreiber als ein Server.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)   
 [Übersicht über die OLE DB-Programmierung](../../data/oledb/ole-db-programming-overview.md)