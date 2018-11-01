---
title: Entwerfen und Erstellen einer Datensatzansicht (MFC-Datenzugriff) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- designing forms
- record views, creating
- forms [C++], designing
- record views, designing
- application wizards [C++], creating record view classes
- designing record views
ms.assetid: 1d6f5439-754f-4b8b-a19d-841a4657827b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c03b85538a795142f5085c93df3a60f4c60481ab
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065849"
---
# <a name="designing-and-creating-a-record-view--mfc-data-access"></a>Entwerfen und Erstellen einer Datensatzansicht (MFC-Datenzugriff)

Sie können die datensatzansichtsklasse mit erstellen die [MFS-Anwendungsassistenten](../mfc/reference/database-support-mfc-application-wizard.md). Wenn Sie einen Anwendungs-Assistenten verwenden, erstellt er die Datensatzansichtsklasse und eine Dialogfeldvorlagen-Ressource (ohne Steuerelemente). Sie müssen den Visual C++-Dialog-Editor verwenden, um der Dialogfeldvorlagen-Ressource Steuerelemente hinzuzufügen. Andererseits, bei Verwendung von **Klasse hinzufügen**, müssen Sie zunächst die Dialogfeldvorlagen-Ressource im Dialogfeld Editor erstellen und dann die datensatzansichtsklasse erstellen.

#### <a name="to-create-your-record-view-with-the-mfc-application-wizard"></a>So erstellen Sie eine Datensatzansicht mit dem MFC-Anwendungs-Assistenten

1. Finden Sie unter [Datenbankunterstützung, MFC-Anwendungsassistenten](../mfc/reference/database-support-mfc-application-wizard.md).

#### <a name="to-design-your-form"></a>So entwerfen Sie ein Formular

1. Finden Sie unter [Dialog-Editor](../windows/dialog-editor.md).

#### <a name="to-create-your-record-view-class"></a>So erstellen Sie eine Datensatzansichtsklasse

1. Finden Sie unter [Hinzufügen eines MFC-ODBC-Consumers](../mfc/reference/adding-an-mfc-odbc-consumer.md).

Die folgenden Themen erläutern die zusätzlichen Informationen zur Verwendung von Datensatzansichten:

- [Datensatzansichten: Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)

- [Datensatzansichten: Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)

- [Datensatzansichten: Füllen eines Listenfelds aus einem zweiten Recordset](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)

## <a name="see-also"></a>Siehe auch

[Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)<br/>
[Recordset (ODBC)](../data/odbc/recordset-odbc.md)<br/>
[Liste der ODBC-Treiber](../data/odbc/odbc-driver-list.md)