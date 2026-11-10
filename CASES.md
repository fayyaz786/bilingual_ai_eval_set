# Evaluation Cases

Each case shows the task, a flawed response that reproduces a common model error, what is wrong, and a corrected reference answer. Arabic text is shown right to left.

## AR01: Idiom translation

**Severity:** Major

**Task:** Translate into Modern Standard Arabic for a business audience.

**Source (English):** Don't worry, preparing the report is a piece of cake.

**Flawed response:**

<p dir="rtl">❌ لا تقلق، إعداد التقرير قطعة من الكعك.</p>

**What is wrong:** Literal translation of an English idiom. An Arabic reader sees an actual piece of cake, so the meaning (very easy) is lost.

**Corrected response:**

<p dir="rtl">✅ لا تقلق، إعداد التقرير أمر سهل للغاية.</p>

---

## AR02: Gender agreement

**Severity:** Major

**Task:** Translate into Modern Standard Arabic.

**Source (English):** Our CEO, Sara, approved the new budget yesterday.

**Flawed response:**

<p dir="rtl">❌ وافق رئيسنا التنفيذي، سارة، على الميزانية الجديدة أمس.</p>

**What is wrong:** The verb and title are masculine (وافق, رئيسنا التنفيذي) although Sara is a woman. Arabic verbs and titles must agree in gender with the subject.

**Corrected response:**

<p dir="rtl">✅ وافقت رئيستنا التنفيذية، سارة، على الميزانية الجديدة أمس.</p>

---

## AR03: Number error (million vs billion)

**Severity:** Critical

**Task:** Translate into Modern Standard Arabic.

**Source (English):** The project budget is SAR 1.5 million.

**Flawed response:**

<p dir="rtl">❌ تبلغ ميزانية المشروع 1.5 مليار ريال سعودي.</p>

**What is wrong:** مليار means billion, not million. The translation makes the budget one thousand times larger, which is a critical error in any financial document.

**Corrected response:**

<p dir="rtl">✅ تبلغ ميزانية المشروع 1.5 مليون ريال سعودي.</p>

---

## AR04: Dropped negation (safety)

**Severity:** Critical

**Task:** Translate this security notice into Modern Standard Arabic.

**Source (English):** Never share your verification code with anyone, including our staff.

**Flawed response:**

<p dir="rtl">❌ شارك رمز التحقق الخاص بك مع أي شخص، بما في ذلك موظفينا.</p>

**What is wrong:** The negation is lost, so the notice now tells customers to share their code, which is the exact opposite of the original and a direct security risk. Minor issue as well: after بما في ذلك the noun should be nominative (موظفونا).

**Corrected response:**

<p dir="rtl">✅ لا تشارك رمز التحقق الخاص بك مع أي شخص أبداً، بما في ذلك موظفونا.</p>

---

## AR05: Register (dialect instead of formal Arabic)

**Severity:** Major

**Task:** اكتب رسالة رسمية قصيرة لعميل تعتذر فيها عن تأخر طلبه. (Write a short formal message to a customer apologising for a delayed order.)

**Flawed response:**

<p dir="rtl">❌ هلا والله، آسفين مرة على التأخير، طلبك بيوصلك بكرة إن شاء الله.</p>

**What is wrong:** The prompt asks for a formal message, but the response is written in casual Gulf dialect (هلا والله, آسفين مرة, بيوصلك, بكرة). The content is fine; the register breaks the instruction.

**Corrected response:**

<p dir="rtl">✅ عزيزي العميل، نعتذر عن التأخر في توصيل طلبك، ونؤكد لك أنه سيصلك غداً بإذن الله. شكراً لتفهمك وصبرك.</p>

---

## AR06: Factual hallucination in Arabic

**Severity:** Critical

**Task:** متى أُعلنت رؤية السعودية 2030، وما هدفها الرئيسي؟ (When was Saudi Vision 2030 announced, and what is its main goal?)

**Flawed response:**

<p dir="rtl">❌ أُعلنت رؤية السعودية 2030 في عام 2017، وتهدف إلى إنهاء اعتماد الاقتصاد على النفط بالكامل بحلول عام 2020.</p>

**What is wrong:** Two factual errors stated with confidence: the vision was announced in April 2016, not 2017, and its goal is to diversify the economy and reduce dependence on oil by 2030, not to end it completely by 2020.

**Corrected response:**

<p dir="rtl">✅ أُعلنت رؤية السعودية 2030 في أبريل 2016، وتهدف إلى تنويع الاقتصاد وتقليل الاعتماد على النفط، إلى جانب تطوير قطاعات مثل السياحة والترفيه والاستثمار، بحلول عام 2030.</p>

---
