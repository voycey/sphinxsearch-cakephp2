I spent a good few hours googling up on how to get this working so here is the fruits of my labour:

Forked from Nabeel Shahzad:

Updated version for the Sphinx Behavior by Vilen Tambovtsev

The original usage page is here:

http://bakery.cakephp.org/articles/xumix/2009/07/11/sphinx-behavior

My Usage
========

```php
public function search() {
            if($this->request->is('post')) {
                $term = $this->request->data['Search']['term'];
                $sphinx = array('matchMode' => 'SPH_MATCH_ALL', 'sortMode' => array('SPH_SORT_EXTENDED' => '@relevance DESC'));
                $paginate = array(
                    'limit' => 10,
                   
                    'contain' => array(
                        
                        'User.id',
                        'User.first_name',
                        'User.last_name',
                        'User.email',
                        'UserDetail.photo',
                    ),
                    'fields'  => array(
                        'id', 'title', 'body', 'image', 'comment_count', 'upvote_count'
                    ),
                    'conditions' => array(),
                    'order' => array('Post.created' => 'desc'),
                    'sphinx' => $sphinx,
                    'search' => $term
                );

                $this->paginate = $paginate;

                $this->set('posts', $this->paginate());
            }
        }
```
