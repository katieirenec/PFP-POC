..  shortname:: Explaining
..  description:: Explaining activity.

.. setup for automatic question numbering.

.. qnum::
   :start: 1
   :prefix: explaining-

Code explaining activity
:::::::::::::::::::::::::


Look at the code below, and try to determine what it does. 

Relevant tags
**********************

Here's the relevant tag from ``https://www.si.umich.edu/people/barbara-ericson``:

.. image:: _static/news_ericson.png
    :scale: 70%
    :align: center
    :alt: Code that you are asked to explain

.. raw:: html

  <pre>
  <pre>Goal: Get a soup from one webpage
  <pre style="background-color:#FCF3CF;">
  <strong># Load libraries for web scraping</strong>
  from bs4 import BeautifulSoup
  import requests
  <strong># Get a soup from <mark style="background-color:#F1948A">a URL</mark></strong>
  url = <mark style="background-color:#F1948A">'https://www.si.umich.edu/people/barbara-ericson'</mark>
  r = requests.get(url)
  soup = BeautifulSoup(r.content, 'html.parser')</pre></pre>
  <pre>Goal: Get info from all tags of a certain type
  <a href="/plan5.html"><pre style="background-color:#D5F5E3;">
  # Get all tags of <mark>a certain type</mark> from the soup
  tags = soup.find_all(<mark>'a', class_='item-teaser--more'</mark>)
  # Collect info from the tags
  collect_info = []
  for tag in tags:
      <strong># Get <mark>info</mark> from tag</strong>
      info = tag.<mark>get('href')</mark>
      collect_info.append(info)</pre></pre></a>
  <pre>Goal: Get a soup from multiple webpages
  <a href="/plan3.html"><pre style="background-color:#FDEBD0;">
  <strong># Get a soup from multiple URLs</strong>
  base_url = <mark>'https://www.si.umich.edu/'</mark>
  endings = <mark>collect_info</mark>
  for ending in endings:
       url = base_url + ending
       r = requests.get(url)
       soup = BeautifulSoup(r.content, 'html.parser')</pre></a></pre>
       <pre>Goal: Get info from all tags of a certain type<a href="/plan5.html"><pre style="background-color:#D5F5E3;">
       <strong># Get all tags of <mark>a certain type</mark> from the soup</strong>
       tags = soup.find_all(<mark>'p'</mark>)
       # Collect info from the tags
       collect_info = []
       for tag in tags:
           <strong># Get <mark>info</mark> from tag</strong>
           info = tag.<mark>text</mark>
           collect_info.append(info)</pre></pre></a>
           <pre>Goal: Print the info<a href="/plan9.html"><pre style="background-color:#D6EAF8;">
           <strong># Print the <mark>info</mark></strong>
           print(<mark>collect_info</mark>)</pre></pre></a>
           </pre>

.. sidebar:: Links to plans
  
    :ref:`plan_2`

    :ref:`plan_3`

    :ref:`plan_4`

    :ref:`plan_5`

    :ref:`plan_9`



.. reveal:: explain_run_code
    :showtitle: If you need a hint, click here.

     You can run the code below and see what happens.

    .. activecode:: explain_code
        :language: python3
        :nocodelens:

        #Get the webpage
        # Load libraries for web scraping
        from bs4 import BeautifulSoup
        import requests
        # Get a soup from a URL 
        url = 'https://www.si.umich.edu/people/barbara-ericson'
        r = requests.get(url)
        soup = BeautifulSoup(r.content, 'html.parser')

        #Extract info from the webpage
        # Get all tags of a certain type from the soup
        tags = soup.find_all('a', class_='item-teaser--more')
        # Collect info from the tags
        collect_info = []
        for tag in tags:
          # Get link from tag
          info = tag.get('href')
          collect_info.append(info)

        #Do something with the info
        # Get a soup from multiple URLs 
        base_url = 'https://www.si.umich.edu/'
        endings = collect_info
        for ending in endings:
            url = base_url + ending 
            r = requests.get(url) 
            soup = BeautifulSoup(r.content, 'html.parser')

            # Get all tags of a certain type from the soup
            tags = soup.find_all('p')
            # Collect info from the tags
            collect_info = []
            for tag in tags:
                # Get text from tag
                info = tag.text
                collect_info.append(info)
            
            # Print the info
            print(collect_info)

.. reveal:: explain_code_cl_reveal_1
        :showtitle: After you've done the activity, click here.
        :hidetitle: Hide question.

        .. poll:: explain_code_cl_1
           :option_1: Very, very low mental effort
           :option_2: Very low mental effort
           :option_3: Low mental effort
           :option_4: Rather low mental effort
           :option_5: Neither low nor high mental effort
           :option_6: Rather high mental effort
           :option_7: High mental effort
           :option_8: Very high mental effort
           :option_9: Very, very high mental effort
           :results: instructor
           
           In solving the preceding problem I invested:

