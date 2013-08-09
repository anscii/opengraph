# Open Graph Protocol helper for PHP

A small library for making accessing of Open Graph Protocol data easier.
Also supports meta "sports:" tags

## Note
Keys with a dash (-) in the name are converted to _ for easy access as a property
in PHP

## Required Extensions
* DOM for parsing

## Usage
	require_once('OpenGraph.php');

	$graph = OpenGraph::fetch('http://www.rottentomatoes.com/m/10011268-oceans/',5);

	if ($graph)
	{
		var_dump($graph->keys());
		var_dump($graph->schema);

		foreach ($graph as $key => $value) {
			if ($key == 'sports:')
			{
				foreach($value as $k => $v)
				{
					echo "$k => $v\n";
				}
			}
			else
			{
				echo "$key => $value\n";
			}
		}
	}
