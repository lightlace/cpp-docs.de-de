---
title: Zuweisen und Freigeben von Arbeitsspeicher für einen BSTR
ms.date: 11/04/2016
f1_keywords:
- bstr
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
ms.openlocfilehash: adc3e1efd032bb3e3e45381da24c5a5b59852375
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216968"
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

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/desktop/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)
