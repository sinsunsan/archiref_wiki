* **indexAction**   
   defaults: { _controller: project:Search:index }
Will call in the controller with the methode **indexAction**

````
class SearchController extends Controller
{
    public function indexAction()
    {
````

* **Render a [[twig]] template**   
`return $this->render('WeCookRecipeBundle:Search:index1.html.twig');`


* [[symphony console]] Command lines tools for symphony
* [[assetic]] : the symphony asset management system