---
title: Zuweisen und Freigeben von Arbeitsspeicher für einen BSTR | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- bstr
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bd299c228b3b388658093f6b138225c10ff38db
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751061"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Zuweisen und Freigeben von Arbeitsspeicher für einen BSTR

Bei der Erstellung `BSTR`s und übergeben Sie sie zwischen COM-Objekte, achten Sie in der zum Behandeln des Arbeitsspeichers, die sie verwenden, um Speicherverluste zu vermeiden. Wenn eine `BSTR` bleibt in einer Schnittstelle, müssen Sie ihren Arbeitsspeicher freigeben, wenn Sie mehr benötigt werden. Aber wenn eine `BSTR` verläuft erfolgreich aus einer Schnittstelle, die das empfangende Objekt übernimmt die Verantwortung für die Verwaltung des Arbeitsspeichers.

Im Allgemeinen die Regeln für das zuordnen und Freigeben von Arbeitsspeicher für zugeordneten `BSTR`sind wie folgt:

- Beim Aufruf an eine Funktion, die erwartet eine `BSTR` -Argument, müssen Sie den Speicher für Zuordnen der `BSTR` vor dem Aufruf und veröffentlichen Sie es anschließend. Zum Beispiel:

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- Beim Aufruf an eine Funktion, die zurückgibt eine `BSTR`, Sie müssen die Zeichenfolge selbst freigeben. Zum Beispiel:

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- Bei der Implementierung einer Funktion, die gibt eine `BSTR`, die Zeichenfolge zuzuweisen, aber es ist nicht frei. Der Empfang die Funktion gibt den Arbeitsspeicher frei. Zum Beispiel:

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)   
[SysAllocString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysallocstring)   
[SysFreeString](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)

