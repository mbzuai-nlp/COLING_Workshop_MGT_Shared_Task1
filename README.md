# Task 1: Binary Multilingual Machine-Generated Text Detection (Human vs. Machine)

[![Code License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-green.svg)](https://raw.githubusercontent.com/mbzuai-nlp/SemEval2024-task8/subtask_A_and_B/LICENSE)

<p align="left" float="left">
  <img src="images/MBZUAI-logo.png" height="40" />
</p>


[News](#news) | [Competition](#competition) | [Important Dates](#important_dates) | [Data Format](#data_format) | [Evaluation Metrics](#scorer_and_official_evaluation_metrics) | [Baselines](#baselines) | [Organizers](#organizers) | [Contacts](#contacts)

Large language models (LLMs) are becoming mainstream and easily accessible, ushering in an explosion of machine-generated content over various channels, such as news, social media, question-answering forums, educational, and even academic contexts. Recent LLMs, such as ChatGPT and GPT-4, generate remarkably fluent responses to a wide variety of user queries. The articulate nature of such generated texts makes LLMs attractive for replacing human labor in many scenarios. However, this has also resulted in concerns regarding their potential misuse, such as spreading misinformation and causing disruptions in the education system. Since humans perform only slightly better than chance when classifying machine-generated vs. human-written text, there is a need to develop automatic systems to identify machine-generated text with the goal of mitigating its potential misuse. 

In the Task 1, we adopt a straightforward binary problem formulation from the previous work of determining whether a given text is generated by a machine or authored by a human. This is the continuation and improvement of the [SemEval Shared Task 8 (subtask A)](https://arxiv.org/abs/2404.14183). We aim to refresh training and testing data with generations from novel LLMs and include new languages.

## NEWS 

### 15 Aug 2024

We have released our training and dev set.

## Competition

The competition will be held on [Kaggle](https://www.kaggle.com/t/23638a8c0d59469196aa67f6bf747f0f).

## <a name="important_dates"></a>Important Dates

- 15th August, 2024: Training/dev set release
- 20th October, 2024: Test set release and evaluation phase starts
- 25th October, 2024: Evaluation phase closes
- 28th October, 2024: Leaderboard to be public
- 15th November, 2024: System description paper submission

## <a name="data_format"></a>Prediction File Format and Format Checkers

A prediction file must be one single JSONL file for all texts. The entry for each text must include the fields "id" and "label".  

The format checkers verify that your prediction file complies with the expected format. They are located in the ```format_checker``` module.

```python
python3 format_checker.py --prediction_file_path=<path_to_your_results_files> 
```

Note that format checkers can not verify whether the prediction file you submit contains predictions for all test instances because it does not have an access to the test file.

## <a name="scorer_and_official_evaluation_metrics"></a>Scorer and Official Evaluation Metrics

The scorers for the subtasks are located in the ```scorer``` modules.
The scorer will report the official evaluation metric and other metrics for a given prediction file.

The **official evaluation metric** is **macro f1-score**. However, the scorer also reports accuracy and micro-F1. 

The following command runs the scorer:
```python
python3 scorer.py --gold_file_path=<path_to_gold_labels> --prediction_file_path=<path_to_your_results_file> 
```

## <a name="baselines"></a>Baselines

Running the Transformer baseline:
 ```
python3 baseline.py --train_file_path <path_to_train_file> --dev_file_path <path_to_development_file> --test_file_path <path_to_test_file> --prediction_file_path <path_to_save_predictions> --model <path_to_model>
 ```

The result for the English setup for RoBERTa is 81.63;

The result for the multilingual setup for XLM-R is 65.46;

## Organizers

- Firoj Alam, Qatar Computing Research Institute, Qatar
- Preslav Nakov, Mohamed bin Zayed University of Artificial Intelligence, UAE
- Nizar Habash, New York University Abu Dhabi, UAE
- Iryna Gurevych, Mohamed bin Zayed University of Artificial Intelligence, UAE; Technical University of Darmstadt, Germany
- Shammur Chowdhury, Qatar Computing Research Institute, HBKU, Qatar
- Artem Shelmanov, Mohamed bin Zayed University of Artificial Intelligence, UAE
- Yuxia Wang, Mohamed bin Zayed University of Artificial Intelligence, UAE
- Ekaterina Artemova, Toloka AI, Netherlands
- Mucahid Kutlu, Qatar University, Qatar
- George Mikros, Hamad Bin Khalifa University, Qatar
- Osama Mohammed Afzal, Mohamed bin Zayed University of Artificial Intelligence, UAE
- Jonibek Mansurov, Mohamed bin Zayed University of Artificial Intelligence, UAE
- Thomas Arnold, Technical University Darmstadt
- Nizar Habash, Mohamed bin Zayed University of Artificial Intelligence
- Hariram Veeramani, UCLA, USA
- Md Tanvirul Alam, Rochester Institute of Technology, USA
- Sahinur Rahman Laskar, UPES, Dehradun, India
- Somnath Banerjee, University of Tartu, Estonia
- Noureldin Elmadany, Arab Academy for Science and Technology, Egypt
- Md Saiful Islam, University of Alberta, USA
- Abdullah I. Alharbi, King Abdulaziz University, Saudi Arabia
- Maram Hasanain, Qatar Computing Research Institute, Qatar
- Alham Fikri Aji, MBZUAI, UAE
- Zhuohan Xie, MBZUAI, UAE
- Tarek Mahmoud, MBZUAI, UAE
- Jinyan Su, Cornell University, USA
- Rui Xing, MBZUAI, UAE
- Jiahui Geng, MBZUAI, UAE
- Yassine El Kheir, Technical University Berlin, Germany
- Giovanni Puccetti, Institute of Information Science and Technology “A. Faedo”, Italy
- Vladislav Mikhailov, University of Oslo, Norway
- Masahiro Kaneko, MBZUAI, UAE
- Ryuto Koike, Tokyo Institute of Technology, Japan
- Orchid Chetia Phukan, Indraprastha Institute of Information Technology Delhi, India
- Koel Dutta Chowdhury, Saarland University, Germany
- Saied Alshahrani, Clarkson University, USA
- Fahad Shamshad, MBZUAI, UAE
- Md Messal Monem Miah, Texas A&M University, USA
- Shah Nawaz, Johannes Kepler University Linz, Austria
- Dr. Bishwa Ranjan Das, Interscience Institute of Management and Technology, India
- Nada Ayman GabAllah, Coventry University, Egypt Branch, Egypt
- Kamel Gaanoun, Institut National de Statistiques et d’Economie Appliquée, Morocco
- Shailja Thakur, IBM Research, USA
- Amr Keleg, University of Edinburgh, UK
- Akim Tsvigun, University of Amsterdam, Netherlands
- Muhammad Amin Nadim, University of Pegaso, Italy
- Marc Franco-Salvador, Symanto Research, Germany
- José Ángel González, Symanto Research, Germany
- Areg Mikael Sarvazyan, Symanto Research, Germany
- Walter Daelemans, University of Antwerp, Belgium
- Piotr Przybyła, Universitat Pompeu Fabra, Italy
- Adaku Uchendu,  MIT Lincoln Laboratory, USA 
- Sheily Panwar, CUC-Ulster University (Doha), Qatar
- Xianjun Yang, UCSB, USA 
- Fatima Haouari, Qatar University
- Fahim Shakil Tamim, IUBAT, Bangladesh
- Zach Johnson, Microsoft, USA
- Abubakarr Jaye, Microsoft, USA 
- Jason Lucas, Penn State University, USA
- Francisco Rangel, Genaios, Germany
- Erum Haris, University of Leeds, UK
- Mohammad Ruhul Amin, Fordham University, USA
- Ram Mohan Rao Kadiyala, University of Maryland, USA

## Contacts

Website: [https://genai-content-detection.gitlab.io](https://genai-content-detection.gitlab.io)  
Email: genai-content-detection@googlegroups.com
