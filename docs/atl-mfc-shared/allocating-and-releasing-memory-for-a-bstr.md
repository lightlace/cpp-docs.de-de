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
ms.openlocfilehash: a7a82acff959d18dcadd3a2c8516a20d60a617d3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491403"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Zuweisen und Freigeben von Arbeitsspeicher für einen BSTR

Wenn Sie s `BSTR`erstellen und diese zwischen COM-Objekten übergeben, müssen Sie den von Ihnen verwendeten Speicher berücksichtigen, um Speicher Verluste zu vermeiden. Wenn eine `BSTR` in einer Schnittstelle bleibt, müssen Sie Ihren Arbeitsspeicher freigeben, wenn Sie damit abgeschlossen sind. Wenn ein jedoch eine `BSTR` Schnittstelle übergibt, übernimmt das empfangende Objekt die Verantwortung für die Speicherverwaltung.

Im allgemeinen lauten die Regeln zum Zuordnen und Freigeben von Arbeitsspeicher `BSTR`, der für s reserviert ist, wie folgt:

- Wenn Sie eine Funktion aufzurufen, die ein `BSTR` -Argument erwartet, müssen Sie den Speicher für `BSTR` das vor dem-Befehl zuordnen und anschließend freigeben. Beispiel:

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- Wenn Sie eine Funktion aufzurufen, die einen `BSTR`zurückgibt, müssen Sie die Zeichenfolge selbst freigeben. Beispiel:

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- Wenn Sie eine Funktion implementieren, die einen `BSTR`zurückgibt, müssen Sie die Zeichenfolge zuordnen, aber nicht freigeben. Die empfangende Funktion gibt den Arbeitsspeicher frei. Beispiel:

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>Siehe auch

[Zeichen folgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/win32/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/win32/api/oleauto/nf-oleauto-sysfreestring)
