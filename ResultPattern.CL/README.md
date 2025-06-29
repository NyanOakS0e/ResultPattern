# ResultPattern

### Result Pattern ဆိုတာဘာလဲ။

> Result Pattern ဆိုတာကတော့ method တစ်ခုကနေ ထွက်လာတဲ့ ရလဒ် (outcome) ကို ဖော်ပြဖို့အတွက် သီးသန့် object တစ်ခုကိုသုံးတဲ့ programming design pattern တစ်ခုဖြစ်ပါတယ်။ Method တွေကနေ တိုက်ရိုက် data (ဥပမာ string or int) ဒါမှမဟုတ် null ကို return လုပ်တာ၊ exception တွေ throw လုပ်တာမျိုးမလုပ်ဘဲ၊ အောင်မြင်ခြင်း/မအောင်မြင်ခြင်း အခြေအနေ၊ data နဲ့ error message တွေအားလုံးကို Result object တစ်ခုတည်းမှာ စုစည်းပြီး return ပြန်ပေးတဲ့ပုံစံဖြစ်ပါတယ်။


### ဘာကြောင့် Result Pattern ကို သုံးသင့်တာလဲ။

- Error Handling ပိုမိုရှင်းလင်းစေခြင်း (Clearer Error Handling): Method တစ်ခုက ဘယ်လို error အမျိုးအစားတွေဖြစ်နိုင်လဲဆိုတာကို Result object ရဲ့ properties တွေ (IsValidationError, IsSystemError) ကနေ ရှင်းရှင်းလင်းလင်းသိနိုင်ပါတယ်။ try-catch block တွေ အများကြီးသုံးစရာမလိုတော့ဘဲ၊ if-else နဲ့ ရလဒ်ကို စစ်ဆေးရုံနဲ့ လုံလောက်ပါတယ်။


- Method Signature က ရည်ရွယ်ချက်ကို ပိုမိုဖော်ပြနိုင်ခြင်း (More Expressive Method Signatures): Method တစ်ခုက Result<Customer> ကို return ပြန်တယ်လို့ရေးထားတာနဲ့၊ ဒီ method ဟာ Customer object ကိုပြန်ပေးနိုင်သလို၊ error တစ်ခုခုလည်း ဖြစ်နိုင်တယ်ဆိုတာကို ကြိုသိနိုင်ပါတယ်။ ဒါက exception တွေ throw လုပ်တဲ့ method တွေထက် ပိုမိုကြိုတင်ခန့်မှန်းရလွယ်ကူစေပါတယ်။

- Code ကို ပိုမိုခိုင်မာစေခြင်း (Robust Code): null check တွေလုပ်ဖို့ မေ့သွားတာမျိုး၊ မမျှော်လင့်ထားတဲ့ exception တွေကြောင့် program crash ဖြစ်တာမျိုးကို လျှော့ချပေးနိုင်ပါတယ်။ ရလဒ်ကို အမြဲတမ်း IsSuccess property နဲ့ အရင်စစ်ဆေးပြီးမှ data ကို သုံးမှာဖြစ်တဲ့အတွက် ပိုစိတ်ချရပါတယ်။

- Error အမျိုးအစားများ ခွဲခြားသိနိုင်ခြင်း (Specific Error Types): သင့်ရဲ့ class မှာ EnumRespType ကိုသုံးထားတဲ့အတွက် ValidationError, NotFound, DuplicateRecord စတဲ့ error အမျိုးအစားတွေကို တိတိကျကျသိနိုင်ပါတယ်။ ဒါကြောင့် error အမျိုးအစားအလိုက် မတူညီတဲ့ logic တွေကို handling လုပ်ဖို့ အရမ်းအဆင်ပြေပါတယ်။