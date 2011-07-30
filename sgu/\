#include <stdio.h>

using namespace std;

#define	INF	(1<<30)
#define min(a, b)	(a) < (b) ? (a) : (b)
#define max(a, b)	(a) < (b) ? (b) : (a)

short n, m, src, dst;
short graph[300][300];

struct junction {
	public:
		short initial_color;
		short initial_time;
		short blue_time, purple_time;
};

struct junction lights[300];
int distance[300], parent[300], marked[300];

void read()
{
	int i;
	char color;

	scanf("%i %i", &src, &dst);
	scanf("%i %i", &n, &m);
	for ( i = 0; i < n; ++i ) {
		scanf("%c %i %i %i", &color, &lights[i].initial_time, &lights[i].blue_time, &lights[i].purple_time);
		if ( color == 'B' )
			lights[i].initial_color = 0;
		if ( color == 'P' )
			lights[i].initial_color = 1;
	}
	for ( i = 0; i < m; ++i ) {
		short row_index, column_index;
		scanf("%i %i", &row_index, &column_index);
		scanf("%i", &graph[row_index][column_index]);
	}
}

int compute_next_time(int crt_time, int src, int dst)
{
	int s_i = lights[src].initial_time;
	int d_i = lights[dst].initial_time;
	int s_r = 0, d_r = 0;

	
}

void dijkstra()
{
	int i, min, min_index;

	for ( i = 0; i < n; ++i ) {
		distance[i] = INF;
		parent[i] = -1;
		marked[i] = 1;
	}

	distance[src] = 0;

	while (1) {
		min = INF;
		min_index = -1;

		// find minimum distance from source
		for ( i = 0; i < n; ++i ) {
			if ( distance[i] < min && marked[i] ) {
				min = distance[i];
				min_index = i;
			}
		}

		// no improvements available
		if ( min == INF )
			break;

		// remove previous found junction
		marked[min_index] = 0;

		for ( i = 0; i < n; ++i ) {
			if ( graph[min_index][i] > 0 ) {
				int alt = compute_next_time(distance[min_index], min_index, i) + graph[min_index][i];
				if ( alt < distance[i] ) {
					distance[i] = alt;
					parent[i] = min_index;
				}
			}
		}
	}
}

int main()
{
	read();
	dijkstra();
	// print distance
	// print path
	return 0;
}
