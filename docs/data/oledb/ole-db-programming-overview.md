---
title: Übersicht über die OLE DB-Programmierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Universal Data Access
- OLE DB, about OLE DB
ms.assetid: a5a69730-2793-4277-a67d-6f3c8edab6df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5fea82dfd7d3f9cdd64d0eab66e44ac1a486abac
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49989891"
---
# <a name="ole-db-programming-overview"></a>Übersicht über die OLE DB-Programmierung

OLE DB ist eine leistungsstarke, COM-basierte datenbanktechnologie. Es bietet eine allgemeine Möglichkeit zum Daten unabhängig von der das Formular zugreifen, in dem es gespeichert ist. In einer typischen Unternehmenssituation wird eine große Menge an Informationen nicht in der Unternehmensdatenbanken gespeichert. Diese Informationen befinden sich in Dateisystemen (z. B. FAT oder NTFS), indizierten sequenziellen Dateien, persönlichen Datenbanken (z. B. in Access), Arbeitsblättern (z. B. in Excel), Anwendungen zur Projektplanung (z. B. Project) sowie in E-Mail-Nachrichten (z. B. in Outlook). OLE DB können Sie jede Art von Datenspeicher in die gleiche Weise zugreifen, solange der Datenspeicher OLE DB-Anbieter verfügt.
  
OLE DB können Sie Anwendungen entwickeln, die Zugriff auf verschiedene Datenquellen, unabhängig davon, ob sie DBMS oder nicht. OLE DB ermöglicht den universellen Zugriff durch die Verwendung von COM-Schnittstellen, die die entsprechenden DBMS-Funktionen für die jeweilige Datenquelle unterstützen. COM reduziert unnötige Verdoppelungen von Diensten und erhöht die Interoperabilität nicht nur zwischen Datenquellen, sondern auch zwischen anderen Anwendungen.  
  
## <a name="benefits-of-com"></a>Vorteile von COM  

Hier setzt COM an. OLE DB stellt eine Gruppe von COM-Schnittstellen dar. Der Datenzugriff mithilfe einer einheitlichen Gruppe von Schnittstellen ermöglicht es Ihnen, eine Datenbank als Matrix kooperierender Komponenten zu organisieren.  
  
OLE DB definiert auf der Grundlage der COM-Spezifikation eine erweiterbare und verwaltbare Reihe von Schnittstellen, die konsistente und wiederverwendbare Teile der DBMS-Funktionalität berücksichtigen und einschließen. Diese Schnittstellen definieren die Grenzen der DBMS-Komponenten, z. B. Zeilencontainer, Abfrageprozessoren und Transaktionskoordinatoren, die einen einheitlichen Transaktionszugriff auf verschiedene Informationsquellen ermöglichen.  
 
## <a name="see-also"></a>Siehe auch  

[OLE DB-Programmierung](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB-Vorlagen](../../data/oledb/ole-db-templates.md)