# csci152-lab-7-solved
**TO GET THIS SOLUTION VISIT:** [CSCI152 Lab 7 Solved](https://www.ankitcodinghub.com/product/csci152-lab-7-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;96952&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSCI152 Lab 7 Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
Goal of this exercise is to change the hash-table based implementation of set into a map. The difference between set and map is that a set can only remember its elements, while a map can remember an associated value.

Mathematically, a map can be viewed a set of pairs with the property that:

(p,q)∈M, (p,q′)∈M ⇒q=q′.

In order to change set into a map, we need to change the implementation of

buckets from

std::vector&lt; std::list&lt; std::string &gt;&gt; buckets;

to

Since std::list&lt; std::pair&lt; std::string, unsigned int &gt; is hard to type and to read, and occurs quite often in the impementation, we will abbreviate it as follows:

using listofpairs = std::list&lt; std::pair&lt; std::string, unsigned int &gt;&gt; ; std::vector&lt; listofpairs &gt; buckets;

1

</div>
</div>
<div class="layoutArea">
<div class="column">
std::vector&lt; std::list&lt; std::pair&lt; std::string, unsigned int &gt;&gt;&gt; buckets;

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
Use this abbreviation whenever possible. It is part of the grading. Download files map.h, map.cpp, main.cpp and Makefile. Class map has the following fields:

class map {

size_t map_size; double max_load_factor;

using listofpairs = std::list&lt; std::pair&lt; std::string, unsigned int &gt;&gt; ; // So that we don’t have to type and read it all the time.

std::vector&lt; listofpairs &gt; buckets; };

As with set, the field map_size contains the total number of key/value pairs in the hash table. max_load_factor defines the maximal value that the load factor map_size / buckets. size( ) can have. It is the average size of a list in the vector. If the load factor becomes bigger than the allowed maximum, the map must be rehashed.

As with set, strings are still compared without distinguishing between upper and lower case. You can reuse equal and hash from the previous task.

1. Study the functions

static listofpairs :: iterator

find( listofpairs&amp; lst, const std::string&amp; key );

static listofpairs :: const_iterator

find( const listofpairs &amp; lst, const std::string&amp; key );

and make sure that you understand how they work. The functions try to find a pair in lst that has key as first element. If they find key, they return the iterator to the pair that contains it. If they don’t find key, they return lst.end( ).

The difference between the two versions of find is that the second version is const. They keyword static means that find can be called without class object (A map in this case.) In order to call find from outside of map, write map::find.

2. Writemethodboolinsert(conststd::string&amp;key,unsignedintval) in file map.cpp. As before, insert must return true, when insertion

takes place, which happens only when key was not present before. Do not

forget to update map_size if (key,val) is inserted.

First call getbucket to find the bucket where key belongs. After that use find to see if key already occurs in it.

For the moment, ignore rehashing. We will come back to that later. 2

</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
<ol start="3">
<li>Implementthemethodstd::ostream&amp;print(std::ostream&amp;out)const. When you are finished, you can remove #if 0 and #endif around std::ostream&amp; operator &lt;&lt; ( std::ostream&amp; out, const map&amp; m )

and print the map.</li>
<li>Implement bool remove( const std::string&amp; key ) in file map.cpp. This function must return true if key was found and removed. Do not
forget to update map_size when key is removed.
</li>
<li>Completemethodboolcontains_key(conststd::string&amp;key)const
in file map.cpp.
</li>
<li>Complete the two at methods in file map.cpp. As usual, two methods are needed, because one is const while the other one is not const. Using the non-const version of at, one can change the value of an existing key, but one can never create a new key using at. Both version of at throw an exception if key is not present.
(Use throw std::out_of_range( “at( ): string not found” );) It must be possible to write:

map german = { { “eins”, 1 }, { “zwei”, 4 }, { “drei”, 3 } }; german. at( “zwei” ) = 2; // Es tut mir leid.

In order to test the case where the exception is thrown, write:

try {

german. at( “hundert” ) = 100; }

catch( std::out_of_range err ) {

std::cout &lt;&lt; “error: ” &lt;&lt; err. what( ) &lt;&lt; “\n”; }

Don’t be lazy at testing all cases, also the exception case. We, together with all the instructors and TAs hate it very much when students don’t test carefully. Your future employer will also hate it.
</li>
<li>Complete unsigned int&amp; operator[] ( const std::string&amp; key ); This method differs from at( ) in the fact that it adds (key,0) if key is not present. Because of this, it is possible to write
german[ “vier” ] = german[ “zwei” ] + german[ “zwei” ]; // Works in other languages as well.
</li>
<li>Complete the method void rehash( size_t newbucketsize ). It should start with
3
</li>
</ol>
</div>
</div>
</div>
<div class="page" title="Page 4">
<div class="layoutArea">
<div class="column">
if( newbucketsize &lt; 4 ) newbucketsize = 4;

std::vector&lt; listofpairs &gt; newbuckets{ newbucketsize }; For the rest, it is the same as rehash for set.

<ol start="9">
<li>Complete method void check_rehash( ). It checks if a rehash is needed.

If yes, it calls rehash with a proper newbucketsize. As with ensure_capacity, make sure that the bucket size is at least doubled in size.</li>
<li>Once you have finished check_rehash, you can add it in every method that potentially adds a key/value pair. These are
bool insert( const std::string&amp; key, unsigned int val ); unsigned int&amp; operator[]( const std::string&amp; key );

There is one problem that you need to test very carefully!

In operator[]( const std::string&amp; key ), the following can happen: key is not found, and a pair (key, 0) is inserted into the hash table. After that, it is possible that a rehash takes place. When this happens, (key, 0) is not any more at the place where it was inserted, and it has to be looked up again, because we need to return a reference to the inserted 0.
</li>
<li>Using main as starting point, you can do some tests, and as always, we want you to be not lazy during testing. It is a habit that will hinder you later in your career.</li>
</ol>
</div>
</div>
<div class="layoutArea">
<div class="column">
4

</div>
</div>
</div>
